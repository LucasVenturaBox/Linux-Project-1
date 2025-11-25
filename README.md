♦ Linux + Nginx Minimal Project

A tiny beginner Linux project: set up a Linux server, configured Nginx to serve a static page, managed permissions, and documented the steps.

♦ What I did
- Created `linux-project-1` and a dedicated user/group  
- Installed and configured Nginx to serve `index.html`  
- Set proper file ownership and permissions  
- Validated the config and handled a `404` caused by an incorrect `root`

♦ Project structure
linux-nginx-server/
├── config/
│ └── nginx-default.conf
├── site/
│ └── index.html
└── README.md

♦ Key commands
- prepare folder and permissions
sudo mkdir -p /srv/website
sudo chown -R www-data:www-data /srv/website
sudo chmod -R 755 /srv/website

- edit nginx config
sudo nano /etc/nginx/sites-available/default

- validate and restart
sudo nginx -t
sudo systemctl restart nginx

♦ Troubleshooting (common cause for 404)
- Nginx serving from a different root (check all server blocks)
- index.html not present or misnamed
- Permissions prevent www-data from reading files

