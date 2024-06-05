
# COAR Notify Integration

The official documentation on how to configure the COAR Notify feature is available at [Lyrasis: COAR Notify - LDN Services Integration](https://wiki.lyrasis.org/display/DSDOC8x/COAR+Notify+-+LDN+Services)
This repository keeps the two patch files to be installed on DSpace 7 to enable/configure the Notify feature.

## Basic Steps to Enable the LDN Feature

1. In `dspace/config/modules/ldn.cfg`, set:

    ```bash
    ldn.enabled = true
    ```

2. In `dspace/config/modules/qaevents.cfg`, set:

    ```bash
    qaevents.enabled = true
    ```

3. In `dspace/config/item-submission.xml`, enable the `coar-notify` step. The following is the definition of the `coarnotify` step. Include this step in the submission definition to need 

    ```xml
	<step-definition id="coarnotify">
	    <heading>submit.progressbar.coarnotify</heading>
	    <processing-class>org.dspace.app.rest.submit.step.NotifyStep</processing-class>
	    <type>coarnotify</type>
	</step-definition>
    ```
## Additional SOLR core configuration
Once the patch for DSpace 7 has been installed a new SOLR core will be available. This core must be configured on the SOLR service in order to allow the indexing of the Events related to the LDN Messages.

The new SOLR core is named `qaevent`

## Branches for the COAR Notify feauture

1. [DSpace 7.6.1 - REST](https://github.com/4Science/DSpace/tree/dspace-7.6.1-coar-notify) 
2. [DSpace 7.6.1 - Angular](https://github.com/4Science/dspace-angular/tree/dspace-7.6.1-coar-notify) 
