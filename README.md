# FTP
Ceci est une application de transfert de fichiers qui illustre d'un **serveur FTP** via les **sockets** en **C**.


<ol>
  <li><h3>Principales réalisations</h3>
    <ul>
      <li><h5>FTP concurrent :</h5>
          NPROC processus attendent la connexion des clients.Le client client connecté sollicite un fichier et le serveur lui renvoie le fichier et des statistiques du transfert sont affichées.
      </li>
      <li><h5>Découpage du Fichier</h5>
        Le transfert se fait par des blocs de 9 octets afin d'éviter la surcharge du serveur
      </li>
      <li><h5>Gestion simple des pannes côtés clients</h5>
        Après un crash et qu'on relance le téléchargement celui ci continu là ou il s'est arrêté
      </li>
      <li><h5>Serveur FTP répartiteur de charge (Maitre-Esclave)</h5>
          <img  weight="20" heigth="20" src="https://github.com/bahmine/FTP/blob/main/repartition.png">
      </li>
      <li> Les commandes <b>ls,pwd,cd,mkdir,rm,put</b> ont été implémentées dans le fichier echo.C en C via les primivites de la bibliothèque <b>dirent.h</b>
      </li>
    </ul>
  </li>
  <li><h3>Test et utilisation</h3>
      <ul>
        <li><h5>utilisation Avec un seul client</h5>
          <ol>
            <li><h6>Serveur</h6>
              <ol>
                <li>make clean</li>
                <li>make</li>
                <li>./slave N°PortSlave autre que N°2121</li>
                <li>./maitre N°PortSlave </li>
              </ol>
            </li>
            <li><h6>Client</h6>
              <ol>
                <li>make clean</li>
                <li>make</li>
                <li>./client hostSeveur hostClient N°PortClient</li>
              </ol>
            </li>
          </ol>
        </li>
        <li><h5>Plusieurs clients</h5>
            <ol>
            <li><h6>Serveur</h6>
              <ol>
                <li>make clean</li>
                <li>make</li>
                <li>./slave N°PortSlave1 autre que N°2121</li>
                <li>./slave N°PortSlave2 autre que N°2121 et N°PortSalve1</li>
                <li>./maitre N°PortSlave1 N°PortSlave2</li>
              </ol>
            </li>
            <li><h6>Client</h6>
              <ol>
                <li>make clean</li>
                <li>make</li>
                <li>./client hostServeur hostClient1 N°PortClient2 autre que 2121</li>
                <li>./client hostServeur hostClient2 N°PortClient2 autre que 2121</li>
              </ol>
            </li>
          </ol>
        </li>
      </ul>
  </li>
</ol>
**NB : Cette application a été entièrement faite sous linux avec le langage C et relire le document memo.pdf pour mieux comprendre
