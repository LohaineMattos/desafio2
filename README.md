//Variáveis globais, vetores e controles
Paciente pacientes[100];
Consulta consultas[1000];
int totalPacientes = 0;
int totalConsultas = 0;

//Funções e procedimentos
void novoPaciente(){
    printf("CPF: ");
    scanf("%s",&pacientes[totalPacientes].cpf);
    printf("Nome: ");
    scanf("%s",&pacientes[totalPacientes].nomeCompleto);
    printf("Telefone: ");
    scanf("%s",&pacientes[totalPacientes].telefone);
    totalPacientes++;
}

void listarPacientes(){
    printf("CPF\tNome Completo\tTelefone\n");
    int i;
    for(i = 0; i < totalPacientes; i++){
        printf("%s\t%s\t%s\n",pacientes[i].cpf,pacientes[i].nomeCompleto,pacientes[i].telefone);    
    }
}

void novoConsulta(){
    printf("DATA (dia/mês/ano): ");
    scanf("%s",&consultas[totalConsultas].data);
    printf("HORA (hoara:minutos): ");
    scanf("%s",&consultas[totalConsultas].hora);
    printf("PACIENTE: ");
    scanf("%s",&consultas[totalConsultas].paciente);
    printf("Nome do Atendente: ");
    scanf("%s",&consultas[totalConsultas].nomeAtendente);
    totalConsultas++;
}

void listarConsultas(){
    printf("DATA\tHORA\tPACIENTE\tNome do Atendente\n");
    int i;
    for(i = 0; i < totalConsultas; i++){
        printf("%s\t %s\t %s\t %s\n",consultas[i].data,consultas[i].hora,consultas[i].paciente,consultas[i].nomeAtendente);    
    }
}

void cancelarConsulta(){
    if(totalConsultas > 0){
    	printf("Consulta excluída.\n");
    	totalConsultas--;
	} else{
		printf("Não há consultas para excluir.\n");
	}
}

int main(){
	setlocale (LC_ALL, "");
    int opcao = 0;
    do{
        printf("1. Cadastrar Paciente\n2. Listar Pacientes\n");
        printf("3. Cadastrar Consulta\n4. Listar Consultas\n");
        printf("5. Cancelar Consulta\n6. Listar Consultas\n");
        printf("7. Encerrar programa\n Escolha uma opção: ");
        scanf("%d", &opcao);
        switch(opcao){
            case 1:
                novoPaciente();
                break;
            case 2: 
                listarPacientes();
                break;
            case 3: 
            	novoConsulta();
            	break;
            case 4: 
				listarConsultas();
				break;
            case 5:
            	cancelarConsulta();
            	break;
            case 6: 
				listarConsultas();
				break;
            case 7: 
				printf("Bye, bye.");
				break;
            default:
            	printf("Bye, bye.");
        }
    }while(opcao != 7);
    return 0;
}
