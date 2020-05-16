Simple Flask App
================

Aplikacja Dydaktyczna wyświetlająca imię i wiadomość w różnych formatach dla zajęć
o Continuous Integration, Continuous Delivery i Continuous Deployment.

- Rozpocząnając pracę z projektem (wykorzystując virtualenv). Hermetyczne środowisko dla pojedyńczej aplikacji w python-ie:

  ::

    # ubuntu, add to ~/.bashrc
    $ source /usr/local/bin/virtualenvwrapper.sh

    # tworzymy hermetyczne środowisko dla bibliotek aplikacji:
    $ mkvirtualenv wsb-simple-flask-app
    $ pip install -r requirements.txt
    $ pip install -r test_requirements.txt

    # albo za pomoca Makefile
    $ make deps

  Sprawdź: `documentację virtualenvwrappera <https://virtualenvwrapper.readthedocs.io/en/latest/command_ref.html>`_ oraz `biblioteki flask <http://flask.pocoo.org>`_.

- Uruchamianie applikacji:

  ::

    # jako zwykły program
    $ python main.py

    # albo:
    $ PYTHONPATH=. FLASK_APP=hello_world flask run

    # albo za pomoca Makefile
    $ make run

- Uruchamianie testów (see: http://doc.pytest.org/en/latest/capture.html):

  ::

    $ PYTHONPATH=. py.test
    $ PYTHONPATH=. py.test  --verbose -s

    # albo za pomoca Makefile
    $ make test

- Kontynuując pracę z projektem, aktywowanie hermetycznego środowiska dla aplikacji py:

  ::

    $ source /usr/local/bin/virtualenvwrapper.sh # nie trzeba, jeśli już w .bashrc
    $ workon wsb-simple-flask-app

    ...

    # deaktywacja virtualenv
    $ deactivate

- Integracja z TravisCI:
    # niezbedny plik .travis.yml-tam wszystkie komendy
  ::
- Budowa dockera lokalnie
    $ make docker_build

- Uruchamianie dockera lokalnie
    $ make docker_run

    # Docker zazwyczaj nie restartujemy, kasujemy i uruchamiamy na nowo:
      $ docker stop hello-world-printer-dev
      $ docker rm hello-world-printer-dev

- Wrzucenie Docker Image do docker hub-a:
    $ export DOCKER_PASSWORD=TWOJE_HASLO
    $ make docker_push


    ...
- Monitoring aplikacji z Statuscake

Pomocnicze
==========

Ubuntu
------

- Instalacja python virtualenv i virtualenvwrapper:

  ::

    $ sudo pip install virtualenv
    $ sudo pip install virtualenvwrapper

- Instalacja dockera: `dockerce howto <https://docs.docker.com/install/linux/docker-ce/ubuntu/>`_



Materiały
=========

- https://virtualenvwrapper.readthedocs.io/en/latest/

.. image:: https://travis-ci.org/Atar91/se_hello_printer_app.svg?branch=master
    :target: https://travis-ci.org/Atar91/se_hello_printer_app

.. image:: https://app.statuscake.com/button/index.php?Track=4RTSF1z2og&Days=1&Design=2
    :target: https://app.statuscake.com/button/index.php
