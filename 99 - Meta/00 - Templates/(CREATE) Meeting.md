<%*
const input = await tp.system.prompt("Meeting date (YYYY-MM-DD)", tp.date.now("YYYY-MM-DD"));
if (!input) return;

const m = moment(input, "YYYY-MM-DD", true);
if (!m.isValid()) {
    new Notice(`Not a valid YYYY-MM-DD date: ${input}`);
    return;
}

const folder = "06 - Notes/Meetings";
const name   = "M" + m.format("YYYYMMDD");
const path   = `${folder}/${name}.md`;

const existing = app.vault.getAbstractFileByPath(path);
if (existing) {
    await app.workspace.getLeaf(false).openFile(existing);
    new Notice(`Opened existing meeting note ${name}`);
    return;
}

const tpl = tp.file.find_tfile("(TEMPLATE) Meeting");
if (!tpl) {
    new Notice("Could not find (TEMPLATE) Meeting");
    return;
}

await tp.file.create_new(tpl, name, true, folder);
%>
