pipeline {

    agent any

    environment {

        MSBuildEXEPath = "C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\BuildTools\\MSBuild\\Current\\Bin\\MSBuild.exe"
        GenexusPath = "C:\\Program Files (x86)\\GeneXus\\GeneXus16BT1"
        KBPath = "C:\\Models\\CapacitacionBT"
        KBEnvironment = 'JavaOracle'
        ExecutionDataFilePath = "C:\\Users\\nsalazar\\Desktop\\Eliminar_cliente.json"
        GXServerUsername = 'local\\sa_jenkins_genexus'
        GXServerPassword = '567NTb0L4L4wjK4hZkAl'
        JUnitTestFilePath = "C:\\Users\\nsalazar\\Desktop\\Result.xml"

        runTestsScript = '"%MSBuildEXEPath%" "%GenexusPath%\\GXtest.msbuild" ' +
						 '/p:KBPath="%KBPath%" ' +
                         '/p:EnvironmentName="%KBEnvironment%" ' +
                         '/p:ExecutionDataFilePath="%ExecutionDataFilePath%" ' +
                         '/p:GXServerUser="%GXServerUsername%" ' +
                         '/p:GXServerPass="%GXServerPassword%" ' +
                         '/p:JUnitTestFilePath="%JUnitTestFilePath%" ' +
                         '/t:RunTestsList'

    }

    stages {
        
        stage('Test KB') {

            steps {

                script {

                    bat label: 'Run tests Script',
                    script: "${env.runTestsScript}"

                }
                
            }

        }
         
    }

}
