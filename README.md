# Systesc
Sistema de realidad virtual para el aprendizaje

//CAMBIO DE ESCENA
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class cambioscena : MonoBehaviour {

	// Use this for initialization
	void Start () {
		
	}
	
	// Update is called once per frame
	void Update () {
		
	}

    public void carganivel(string pNombreNivel)
    {
        SceneManager.LoadScene(pNombreNivel);
	}


}


//CONTROL
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class VRlookWalk : MonoBehaviour {

    public Transform vrCamera;
    public float toggleAngle = 30.0f;
    public float speed = 3.0f;
    public bool moveForward;

    private CharacterController cc;

    private void Start()
    {
        cc = GetComponent<CharacterController>();
    }

    void Update()
    {
        if (vrCamera.eulerAngles.x >= toggleAngle && vrCamera.eulerAngles.x < 90.0f)
        {
            moveForward = true;
        }
        else
        {
            moveForward = false;
        }

        if(moveForward)
        {
            Vector3 forward = vrCamera.TransformDirection(Vector3.forward);
            cc.SimpleMove(forward * speed);

        }
    }
}

// REFERENCIA
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class NewBehaviourScript : MonoBehaviour {

	// Use this for initialization
	void Start () {
		
	}
	
	// Update is called once per frame
	void Update () {
		
	}
}
