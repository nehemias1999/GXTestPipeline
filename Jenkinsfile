pipeline {

    agent any

    environment {

        // Ajustar estas rutas según tu instalación

        MSBuildEXEPath = "C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\BuildTools\\MSBuild\\Current\\Bin\\amd64\\MSBuild.exe"
        GenexusPath = "C:\\Program Files (x86)\\GeneXus\\GeneXus16BT1"
        DbaseServerUsername = 'local\\sa_jenkins_genexus'
        DbaseServerPassword = '567NTb0L4L4wjK4hZkAl'
        WorkingDirectory = "C:\\Models\\CapacitacionBT"
        WorkingVersion = 'Estimaciones'
        WorkingEnvironment = 'JavaOracle'
        ServerUsername = 'local\\sa_jenkins_genexus'
        ServerPassword = '567NTb0L4L4wjK4hZkAl'

        runTestsScript = '"%MSBuildEXEPath%" "%GenexusPath%"\\GXtest.msbuild ' +
						 '/p:KBPath="%WorkingDirectory%" ' +
						 '/p:EnvironmentName="%WorkingEnvironment%" ' +
						 '/p:TestType="Unit" ' +
						 '/p:JUnitTestFilePath="C:\\Users\\nsalazar\\Desktop\\Eliminar cliente.json" ' +
						 '/p:GXServerUser="%ServerUsername%" ' +
						 '/p:GXServerPass="%ServerPassword%" ' +
                         '/t:RunTests'

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
