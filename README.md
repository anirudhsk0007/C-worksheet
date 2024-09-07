using UnityEngine;

public class CharacterMovement : MonoBehaviour
{
    public float moveSpeed = 5f; // Speed of character movement

    private void Update()
    {
        // Get input from the user
        float moveHorizontal = Input.GetAxis("Horizontal"); // A/D or Left/Right arrow keys
        float moveVertical = Input.GetAxis("Vertical");     // W/S or Up/Down arrow keys

        // Create a movement vector
        Vector3 movement = new Vector3(moveHorizontal, 0f, moveVertical);

        // Normalize the movement vector to maintain consistent speed in all directions
        movement = movement.normalized * moveSpeed * Time.deltaTime;

        // Move the character
        transform.Translate(movement, Space.World);
    }
}
