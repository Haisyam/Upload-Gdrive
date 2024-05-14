Code untuk di App Script Google `Kode.gs`
   ```js
   function doPost(e) {
  const folderId = "id gdrive";  //ambil dari link gdrive

  const blob = Utilities.newBlob(JSON.parse(e.postData.contents), e.parameter.mimeType, e.parameter.filename);
  const file = DriveApp.getFolderById(folderId).createFile(blob);
  const responseObj = {filename: file.getName(), fileId: file.getId(), fileUrl: file.getUrl()};
  return ContentService.createTextOutput(JSON.stringify(responseObj)).setMimeType(ContentService.MimeType.JSON);
}
   ```
CC TikTok: [Ex-Mamang Ngoding](https://www.tiktok.com/@gikspedia)

Video Tutorial: [Tonton Video](https://vt.tiktok.com/ZSYd2BRk6/)
