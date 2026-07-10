// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

/**
 * @title EcoCarbon
 * @dev Protocolo de incentivos para la reducción de huella de carbono en la UNMSM.
 * Diseñado para mitigar la asimetría de información y reducir costos de transacción.
 */
contract EcoCarbon {
    
    // Variables de estado
    string public constant name = "Eco-Carbon UNMSM Token";
    string public constant symbol = "ECO";
    address public immutable regulator; // UNMSM Admin

    // Mapeo para tracking de impactos (Eficiencia O(1))
    mapping(address => uint256) public balances;
    mapping(address => uint256) public totalRecycledKg;

    // Eventos para trazabilidad (Necesario para el Frontend)
    event RecyclingRegistered(address indexed user, uint256 kgAmount, uint256 pointsRewarded);

    constructor() {
        regulator = msg.sender;
    }

    modifier onlyRegulator() {
        require(msg.sender == regulator, "Solo la entidad reguladora puede validar");
        _;
    }

    /**
     * @notice Registra acción de reciclaje y emite incentivos
     * @param user Dirección del estudiante/usuario
     * @param kg Cantidad de material reciclado en kg
     */
    function registerRecycling(address user, uint256 kg) public onlyRegulator {
        uint256 reward = kg * 10; // Factor de incentivo (1kg = 10 ECO)
        
        balances[user] += reward;
        totalRecycledKg[user] += kg;

        emit RecyclingRegistered(user, kg, reward);
    }

    // Consultas de estado
    function getBalance(address user) external view returns (uint256) {
        return balances[user];
    }
}
