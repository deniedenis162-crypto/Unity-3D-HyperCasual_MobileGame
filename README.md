# Unity 3D Mobile Template for Hyper Casual gameusing UnityEngine;

public class MotorcycleController : MonoBehaviour
{
    public float speed = 10f;         // viteză înainte
    public float turnSpeed = 50f;     // viteza la înclinare
    public float jumpForce = 5f;      // sărituri (dacă vrei off-road)
    private Rigidbody rb;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        // Mișcare înainte
        rb.MovePosition(transform.position + transform.forward * speed * Time.deltaTime);

        // Înclinare stânga/dreapta (tilt telefon sau săgeți)
        float h = Input.GetAxis("Horizontal"); // stânga/dreapta
        transform.Rotate(0, h * turnSpeed * Time.deltaTime, 0);

        // Salt (dacă e off-road)
        if (Input.GetButtonDown("Jump") && Mathf.Abs(rb.velocity.y) < 0.01f)
        {
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
        }
    }
}



Overview
This project is a hypercasual game created using Unity 3D. The game features an infinite generation of obstacles that the player must dodge. I've developed scripts for handling obstacles, player controls, and animations triggered when the player collides with obstacles. The game utilizes Unity-provided functions to enhance its functionality and performance.

Features
Infinite obstacle generation
Player control scripts
Collision detection and obstacle interaction
Unity-provided functions integration

Demo

https://github.com/LoviceSunuwar/Unity-3D-HyperCasual_MobileGame/assets/53461002/ce2ba3b0-1f94-46e4-865e-1e39049ed8b7


![Screenshot 2023-12-25 at 8 45 06 PM](https://github.com/LoviceSunuwar/Unity-3D-HyperCasual_MobileGame/assets/53461002/99e90fbf-83c3-4759-846f-3f8c212bafff)


![Screenshot 2023-12-28 at 3 14 43 PM](https://github.com/LoviceSunuwar/Unity-3D-HyperCasual_MobileGame/assets/53461002/2d7d75df-6f39-4f56-94ea-0b9414a6ea68)
