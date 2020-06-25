# EmailAutomation2
Create a workflow that:

--    Reads the 6th page of "Session 11 - exercise 2 - UiPathOrchestratorAzureInstallationGuide2016.1.pdf" (in the attachment)

--    Reads the 2nd page of "Session 11 - exercise 2 - ScannedDoc.pdf" (in the attachment)

--    Sends an email with both documents attached and with the text from point 1 and text from point 2 as Body


In UiPath Studio, create a new project and perform following steps:

The first PDF document we are trying to extract text from is a native pdf, (the text is selectable, 
the doc is created from a Word document probably, etc) so we will use the dedicated activity for this case, 
Read PDF Text.

  --  We click on the dots next to File Name property and browse to the location we have the Orchestrator 
      Installation Guide document saved at.
      
  --  We replace the Range property value from “All” to 6, in order to read just the page 6 from the document.
  
  --  We create a variable in the Output, to save the retrieved text for later.

The second pdf document we are trying to extract from is a scanned pdf (everything is a picture, you cannot 
select any element, etc) so we will use the dedicated activity for this case, Read PDF With OCR.

  --  click on the dots next to File Name property and browse to the location we have the “Scanned.pdf” 
      document saved at.

  --  We replace the Range property value from “All” to 2, in order to read just the page 2 from the document.

  --  We create a variable in the Output, to save the retrieved text for later.
  
  --  We add 2 Log Message windows with Log Level set to 'Info' and select 2 individual String variables (1 for each
      PDF files)

  --  We add a Send Outlook Mail Message (can be any Send XXX Mail Message activity)set the To property.

  --  Set the Subject property.

  --  Set the Body property to concatenated variables that keep the text pieces read from the two documents 
      installationPDFText + invoicePDFText.
