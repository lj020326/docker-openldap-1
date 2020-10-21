#!/usr/bin/env groovy

//@Library("pipeline-automation-lib@develop")_
@Library("pipeline-automation-lib")_

import com.dettonville.api.pipeline.utils.logging.LogLevel
import com.dettonville.api.pipeline.utils.logging.Logger
import com.dettonville.api.pipeline.utils.JsonUtils

Logger.init(this, LogLevel.INFO)
//Logger.init(this, LogLevel.DEBUG)
Logger log = new Logger(this)

String configYmlStr="""
---
pipeline:
  logLevel: DEBUG

  buildImageList:
#    - buildImageLabel: "docker-openldap"
#      buildDir: "image"

    - buildDir: "image"

"""

Map configSettings = readYaml text: configYmlStr
Map config=configSettings.pipeline

log.info("config=${JsonUtils.printToJsonString(config)}")

buildDockerImage(config)
