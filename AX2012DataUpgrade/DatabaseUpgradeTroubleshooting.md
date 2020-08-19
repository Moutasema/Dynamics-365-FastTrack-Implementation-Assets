# Troubleshooting steps and mitigation during data upgrade run and post data upgrade
What is this document about and who's the intended audience

## Error 1 Deployable package is blocked
Request for the permission of type 'System.Security.Permissions.FileIOPermission, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b4342343gdsdg' failed.
   at System.Security.CodeAccessSecurityEngine.Check(Object demand, StackCrawlMark& stackMark, Boolean isPermSet)
   at System.Security.CodeAccessPermission.Demand()
   at System.Security.Permissions.FileIOPermission.QuickDemand(FileIOPermissionAccess access, AccessControlActions control, String[] fullPathList, Boolean checkForDuplicates, Boolean needFullPath)
   at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize)
   at System.Xml.XmlDownloadManager.GetStream(Uri uri, ICredentials credentials, IWebProxy proxy, RequestCachePolicy cachePolicy)
   at System.Xml.XmlUrlResolver.GetEntity(Uri absoluteUri, String role, Type ofObjectToReturn)
   at System.Xml.XmlSecureResolver.GetEntity(Uri absoluteUri, String role, Type ofObjectToReturn)
   at System.Xml.XmlTextReaderImpl.FinishInitUriString()
   at System.Xml.XmlReaderSettings.CreateReader(String inputUri, XmlParserContext inputContext)
   at Microsoft.Dynamics.AX.AXInstallationInfo.ServiceModelInstallationInfo.InitFromFile(String filePath)
   at Microsoft.Dynamics.AX.AXInstallationInfo.AXInstallationInfo.GetInstalledServiceModel()
   at Microsoft.Dynamics.AX.AXUpdateInstaller.Program.InstallUpdate(String[] args)
   at Microsoft.Dynamics.AX.AXUpdateInstaller.Program.Main(String[] args).
### Solution
	After you download the deployable package as zip file, right-click it, and then select Properties. Then, in the Properties dialog box, on the General tab, select Unblock to unlock the files.
