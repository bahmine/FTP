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
          <img height="20" weight="20" src="https://github.com/bahmine/FTP/blob/main/repartition.png">
      </li>
    </ul>
  </li>
  <li><h3>Test et utilisation</h3>
  </li>
</ol>
