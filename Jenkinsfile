node {
     stage ( " Git checkout to container ${container_name}....") {
     sh " git clone https://github.com/muralidharansomasundaram/scriptlocation.git --branch ${git_branch}"
     sh "oc script.sh \$(oc get pods -n ${container_namespace} -l name=${container_name} | awk '{print $1 }' | tail -n1):/var -n ${container_namespace}"
     sh "oc exec \$(oc get pods -n ${container_namespace} -l name=${container_name} | awk '{print $1 }' | tail -n1) -n ${container_namespace} --bash -c 'sh script.sh &> run.log'"
     }
     }
