Configuration
=============

``ALLAUTH_2FA_TEMPLATE_EXTENSION``
----------------------------------

ALlows you to override the extension for the templates used by the internal
views of django-allauth-2fa.

Defaults to ``ACCOUNT_TEMPLATE_EXTENSION`` from allauth, which is ``html`` by
default.

This can be used to allow a different template engine for 2FA views.

``ALLAUTH_2FA_ALWAYS_REVEAL_BACKUP_TOKENS``
-------------------------------------------

Whether to always show the remaining backup tokens on the
Backup Tokens view, or only when they're freshly generated.

Defaults to ``True``.

``ALLAUTH_2FA_QRCODE_TYPE``
-------------------------------------------

Configure the generation of the QR code image.

Defaults to ``data`` for a base64 encoded SVG image using the 'data:'
protocol.  Setting this to ``file`` will use an SVG file stored in
``settings.MEDIA_ROOT/qrcodes/``.

Use of the 'data:' protocol must be specifically allowed by sites that
are using a strict CSP.  By providing the image as a file, it is
covered by the typical 'self' directives in a strict CSP.  The file is
generated with a UUID4 filename to avoid predictability.  Since all
files are generated in the same directory, a periodic task to remove
all files older than some time can be used to delete old QR codes.
