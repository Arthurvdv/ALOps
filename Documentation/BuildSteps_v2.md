    # Build Steps Overview
    Let's describe all the Build Steps that we have at our disposal

    ## List and describe all build steps
    Here is a list of all build steps you have at your disposal when you use ALOps

        ### ALOps Tasks
    - ALOps App Compiler
  * Compile Business Central extension(s) from AL code.
  * YAML Template: 
    ```yaml
            - task: ALOpsAppCompiler@2
            displayName: 'ALOps App Compiler'
          inputs:
            artifactversion:                      # BC/NAV Version, eg: 9, 10.4, NAV2016, 16.4.24524. $(artifactversion) $(artifactversion)
            artifacttype: OnPrem                  # Set Artifact Type. $(artifacttype) $(artifacttype)
            artifactcountry:                      # The Country for the Artifact. $(artifactcountry) $(artifactcountry)
            versionselect: Latest                 # The version to be selected from the Artifacts. $(versionselect) $(versionselect)
            alternativevsixurl:                   # Alternative VSIX download url. Overrules BC Artificat VSIX. 'Latest' can be specified. $(alternativevsixurl) $(alternativevsixurl)
            alsourcepath: $(System.DefaultWorkingDirectory)#  $(alsourcepath) $(alsourcepath)
            ruleset:                              # Overrule the Ruleset from VSCode settings. Path relative to [alsourcepath] $(ruleset) $(ruleset)
            suppresswarnings: KEEP                # Overrule the 'suppresswarnings' setting. $(suppresswarnings) $(suppresswarnings)
            appversiontemplate: 1.0.*.0           # Template for versioning Apps. '*' is replaced by the current Build Number. $(appversiontemplate) $(appversiontemplate)
            updatebuildnumber: True               # Update the Build number with the current version. $(updatebuildnumber) $(updatebuildnumber)
            appfilenametemplate: %APP_PUBLISHER%_%APP_NAME%_%APP_VERSION%_%BC_TYPE%_%BC_VERSION%_%BC_COUNTRY%.app# Template for App filename. $(appfilenametemplate) $(appfilenametemplate)
            alcodeanalyzer:                       # AL Analyzer(s) used for compiling. (Example: CodeCop,UICop) $(alcodeanalyzer) $(alcodeanalyzer)
            ignorepragmas:                        # Report Suppressed Diagnostics: diagnostics suppressed in source code should be emitted. $(ignorepragmas) $(ignorepragmas)
            showmycode: Keep                      # Overrule ShowMyCode by setting other option than 'Keep'. $(showmycode) $(showmycode)
            resourceexposurepolicy_allowdebugging: Keep# Overrule allowDebugging by setting other option than 'Keep'. $(resourceexposurepolicy_allowdebugging) $(resourceexposurepolicy_allowdebugging)
            resourceexposurepolicy_allowdownloadingsource: Keep# Overrule allowDownloadingSource by setting other option than 'Keep'. $(resourceexposurepolicy_allowdownloadingsource) $(resourceexposurepolicy_allowdownloadingsource)
            resourceexposurepolicy_includesourceinsymbolfile: Keep# Overrule includeSourceInSymbolFile by setting other option than 'Keep'. $(resourceexposurepolicy_includesourceinsymbolfile) $(resourceexposurepolicy_includesourceinsymbolfile)
            internalsvisibleto: Keep              # Remove internalsVisibleTo by setting other option than 'Keep'. $(internalsvisibleto) $(internalsvisibleto)
            preprocessorsymbols:                  # Overwrite the preprocessorSymbols in app.json, comma seperated string. Set to 'NONE' to remove. $(preprocessorsymbols) $(preprocessorsymbols)
            applicationinsightskey:               # Overwrite the ApplicationInsightsKey in app.json. Set to 'NONE' to remove InsightsKey. $(applicationinsightskey) $(applicationinsightskey)
            alcachepath: $(System.DefaultWorkingDirectory)#  $(alcachepath) $(alcachepath)
            publishartifact: True                 # Publish generated App Artifact to DevOps. $(publishartifact) $(publishartifact)
            publishxlif: False                    # Publish generated XLIF to DevOps. $(publishxlif) $(publishxlif)
            failonwarnings: False                 # Fail task when any warning occurs. $(failonwarnings) $(failonwarnings)
            storageaccount:                       # Non Default Storage Account. $(storageaccount) $(storageaccount)
            sastoken:                             # SAS Token used to access Storage Account. $(sastoken) $(sastoken)
            printappmanifest: True                # Print the final app.json before compile. $(printappmanifest) $(printappmanifest)
            outputalclogs: True                   # Output ALC logs. $(outputalclogs) $(outputalclogs)
            additionalprobingpaths:               # Add additional Assembly probing Paths. $(additionalprobingpaths) $(additionalprobingpaths)
    ```
- ALOps Repository Publish Extension
  * Publish extension to ALOps Repository.
  * YAML Template: 
    ```yaml
            - task: ALOpsRepositoryPublish@2
            displayName: 'ALOps Repository Publish Extension'
    ```

