---
<?php

$botToken = "8107961909:AAE_rCJHhok1kvexhXsRDBST9MqI_4aI6Sg";
$chatID   = "8449961028";

// data dari form
$nama  = $_POST['nama'];
$hp    = $_POST['hp'];
$pesan = $_POST['pesan'];

// isi pesan
$message = "
📩 *Pesan Baru dari Website*

👤 Nama: $nama
📱 HP: $hp
💬 Pesan: $pesan
";

// kirim ke telegram
$url = "https://api.telegram.org/bot$botToken/sendMessage";

$data = [
    'chat_id' => $chatID,
    'text' => $message,
    'parse_mode' => 'Markdown'
];

$options = [
    'http' => [
        'header'  => "Content-type: application/x-www-form-urlencoded\r\n",
        'method'  => 'POST',
        'content' => http_build_query($data),
    ],
];

$context = stream_context_create($options);
$result = file_get_contents($url, false, $context);

if ($result) {
    echo "Pesan berhasil dikirim!";
} else {
    echo "Gagal mengirim pesan!";
}

?>
title: '{% data variables.product.prodname_codespaces %} documentation'
shortTitle: '{% data variables.product.prodname_codespaces %}'
intro: >-
  Create a codespace to start developing in a secure, configurable, and
  dedicated development environment that works how and where you want it to.
introLinks:
  overview: /codespaces/about-codespaces/what-are-codespaces
  quickstart: /codespaces/quickstart
layout: discovery-landing
includedCategories:
  - Get started
  - Create and manage codespaces
  - Write code in a codespace
  - Customize your codespace
  - Set up dev containers for a project
  - Speed up codespace creation with prebuilds
  - Manage codespaces for your organization
  - Troubleshoot codespaces
carousels:
  recommended:
    - /codespaces/quickstart
    - /codespaces/about-codespaces/what-are-codespaces
    - /codespaces/about-codespaces/understanding-the-codespace-lifecycle
    - /codespaces/developing-in-a-codespace/creating-a-codespace-for-a-repository
    - /codespaces/developing-in-a-codespace/creating-a-codespace-from-a-template
    - /codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers
    - /codespaces/developing-in-a-codespace/using-source-control-in-your-codespace
    - /codespaces/managing-codespaces-for-your-organization/enabling-or-disabling-github-codespaces-for-your-organization
    - /codespaces/reference/security-in-github-codespaces
communityRedirect:
  name: Provide GitHub Feedback
  href: 'https://github.com/orgs/community/discussions/categories/codespaces'
redirect_from:
  - /github/developing-online-with-github-codespaces
  - /github/developing-online-with-codespaces
  - >-
    /codespaces/developing-in-a-codespace/using-github-codespaces-in-your-jetbrains-ide
  - /codespaces/reference/using-the-github-codespaces-plugin-for-jetbrains
  - /codespaces/guides
  - /video-transcripts/transcript-codespaces-your-instant-dev-box-in-the-cloud
versions:
  fpt: '*'
  ghec: '*'
children:
  - /quickstart
  - /about-codespaces
  - /developing-in-a-codespace
  - /customizing-your-codespace
  - /setting-your-user-preferences
  - /setting-up-your-project-for-codespaces
  - /prebuilding-your-codespaces
  - /managing-your-codespaces
  - /managing-codespaces-for-your-organization
  - /reference
  - /troubleshooting
  - /the-githubdev-web-based-editor
---
