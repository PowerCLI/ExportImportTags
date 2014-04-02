ExportImportTags
================

PowerCLI Script to Export and Import vSphere Tag information.

using the attached script “ExportImportTags.ps1” you will be able to export your tag configuration from one VC and then import it to another (one or multiple).

To use the script – simply download it and save it in a folder of your preference. Start PowerCLI and load the script:

. <path_to_folder>\ExportImportTags.ps1

Then connect to the VC you want to export tags from:

$sourceVC = Connect-VIServer <connection_parameters>

To export all tags use the Export-Tags function. It accepts two parameters, the server from which to export the tags and a destination file where to save them:

Export-Tags –Server $sourceVC –Destination C:\vc1_tags.txt

Then connect to the VC(s) that you want to import those tags to:

$destinationVC = Connect-VIServer <connection_parameters>

To import the tags use the Import-Tags function. It accepts two parameters, the server on which to import the tags and a source file from which to read them (the file produced by Export-Tags earlier):

Import-Tags –Server $destinationVC –Source C:\vc1_tags.txt

That’s it! You now have the same tag configuration across all your VCs.

For more information on Tags make sure you check out the blog post here: https://blogs.vmware.com/PowerCLI/2014/03/using-vsphere-tags-powercli.html
