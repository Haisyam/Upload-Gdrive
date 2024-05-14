Code untuk di App Script Google `Kode.gs`
   ```js
   function doPost(e) {
  const folderId = "1yYe8JRCGs-9EOvaJF6xSiZANTQ9-wuOA";  //ambil dari link gdrive

  const blob = Utilities.newBlob(JSON.parse(e.postData.contents), e.parameter.mimeType, e.parameter.filename);
  const file = DriveApp.getFolderById(folderId).createFile(blob);
  const responseObj = {filename: file.getName(), fileId: file.getId(), fileUrl: file.getUrl()};
  return ContentService.createTextOutput(JSON.stringify(responseObj)).setMimeType(ContentService.MimeType.JSON);
}
   ```
