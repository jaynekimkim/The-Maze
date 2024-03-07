# The-Maze
Siyoo and Jayne's Game
using UnityEngine;

public class BallMovement : MonoBehaviour
{
    public float moveSpeed = 5f;

    void Update()
    {
        // Get input from the player
        float verticalInput = Input.GetAxis("Vertical");

        // Move the ball based on the input
        Vector3 movement = new Vector3(0f, verticalInput, 0f) * moveSpeed * Time.deltaTime;
        transform.Translate(movement);

        // Optionally, clamp the ball's position to keep it within certain bounds
        // For example, if you want to keep the ball between -5 and 5 on the Y-axis:
        transform.position = new Vector3(transform.position.x, Mathf.Clamp(transform.position.y, -5f, 5f), transform.position.z);
    }
}
