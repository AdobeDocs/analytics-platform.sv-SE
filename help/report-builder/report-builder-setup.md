---
title: Konfigurera Report Builder i Customer Journey Analytics
description: Beskriver hur du konfigurerar Report Builder i Customer Journey Analytics
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 99aedc28-05d5-4fc1-8c32-6e5d1d3b0f84
solution: Customer Journey Analytics
source-git-commit: 49a35a256758b259dfb2133658bae617315774e4
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Konfigurera Report Builder

Du kommer snabbt åt Report Builder via Excel-tilläggsmenyn.

## Krav

Report Builder för Customer Journey Analytics stöds av följande operativsystem och webbläsare.

### macOS

- macOS Version 10.x eller senare
- Alla Excel-versioner

### Windows

- Windows 10, version 1904 eller senare
- Excel version 2106 eller senare

  Alla Excel-användare med Windows-datorer måste installera Microsoft Edge Webview2 för att kunna använda tillägget. Så här installerar du styrenheten:

   1. Gå till <https://aka.ms/webview2installer>.
   1. Välj och hämta Evergreen Standalone Installer.
   1. Följ installationsanvisningarna.

### Webbkontor

- Stöder alla webbläsare och versioner


## Excel-tillägg för Report Builder

Du måste installera Report Builder Excel-tillägget för att kunna använda Report Builder för Customer Journey Analytics. När du har installerat tillägget Report Builder Excel kan du komma åt Report Builder från en öppen Excel-arbetsbok.

### Hämta och installera tillägget Report Builder

Hämta och installera tillägget Report Builder

1. Starta Excel och öppna en ny arbetsbok.

1. Välj Infoga > Hämta tillägg.

1. I dialogrutan för Office-tillägg väljer du fliken Store.

1. Sök efter &quot;Report Builder&quot; och klicka på Lägg till.

1. Klicka på Fortsätt i dialogrutan Licensvillkor och Integritetspolicy.

**Om fliken Store inte visas**

1. I Excel väljer du Arkiv > Konto > Hantera inställningar.

1. Markera rutan bredvid&quot;Aktivera valfria anslutna upplevelser&quot;

1. Starta om Excel.

**Om din organisation blockerar åtkomsten till Microsoft Store**

Kontakta IT-avdelningen eller säkerhetsteamet och be om godkännande av tillägget Report Builder. När godkännande har beviljats väljer du fliken Administratörshanterad i dialogrutan för Office-tillägg.

![Fliken Administratörshanterad i dialogrutan för Office-tillägg.](./assets/image1.png)

När du har installerat tillägget Report Builder visas ikonen Report Builder i Excel-menyfliksområdet på fliken Hem.

![Ikonen Report Builder i Excel](./assets/rb_app_icon.png)

## Logga in i Report Builder

När du har installerat tillägget Report Builder for Excel för din operativplattform eller webbläsare följer du de här stegen för att logga in på Report Builder.

1. Öppna en Excel-arbetsbok.

1. Klicka på ikonen Report Builder för att starta Report Builder.

1. I verktygsfältet i Adobe Report Builder klickar du på **Inloggning**.

   ![Klicka på inloggningsknappen för Report Builder.](./assets/rb_login.png)

1. Ange din kontoinformation för Adobe Experience ID. Kontoinformationen bör överensstämma med dina Customer Journey Analytics-uppgifter.

   ![Din inloggningsikon och organisation.](./assets/image4.png)

När du har loggat in visas din inloggningsikon och organisation högst upp på panelen

## Byt organisation

När du loggar in första gången loggas du in på den standardorganisation som tilldelats din profil.

1. Klicka på namnet på organisationen som visas när du loggar in.

1. Välj en organisation i listan över tillgängliga organisationer. Endast organisationer som du har åtkomst till listas.

   ![Listan över organisationer som du har åtkomst till.](./assets/image5.png)

## Logga ut

Du kan logga ut från Report Builder från användarprofilen.

1. Spara ändringar i alla öppna arbetsböcker.

1. Klicka på avatarikonen för att visa din användarprofil.

   ![Din användarprofilavatar och knappen Logga ut.](./assets/image6.png)

1. Klicka **Logga ut**.
