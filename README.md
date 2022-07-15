//Movimento-do-player-CharacterController-
//PlayerMovement
// using c#
// unity

public class Teste : MonoBehaviour
{
    public float speed = 5;
    public Vector3 _input, direction;
    public CharacterController controller;

    void Update()
    {
        _input = new Vector3(Input.GetAxis("Horizontal"), Input.GetAxis("Jump"), Input.GetAxis("Vertical"));

        direction = transform.right * _input.x + transform.forward * _input.z;

        direction = Vector3.ClampMagnitude(direction, 1);

        direction *= speed;

        controller.Move(direction * Time.deltaTime);

    }
}
