FROM odoo:18

USER root

RUN apt-get update && apt-get install -y --no-install-recommends \
    fonts-dejavu-core fonts-dejavu-extra gsfonts fonts-liberation fontconfig \
 && fc-cache -f -v \
 && rm -rf /var/lib/apt/lists/*

COPY --chown=odoo:odoo ../../vendor/OCB /opt/ocb

RUN mkdir -p /etc/odoo
COPY --chown=odoo:odoo ../../src/configs/odoo.conf /etc/odoo/odoo.conf

RUN pip install --no-cache-dir -r /opt/ocb/requirements.txt || true

RUN chown -R odoo:odoo /var/lib/odoo

USER odoo

CMD ["python3", "/opt/ocb/odoo-bin", "-c", "/etc/odoo/odoo.conf"]
