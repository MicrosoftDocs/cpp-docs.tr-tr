---
title: "Uzak Linux bilgisayarınıza bağlayın | Microsoft Docs"
ms.custom: 
ms.date: 11/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6dce0c1c190854b7927c6e023edd76c9d1cb5645
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="connect-to-your-remote-linux-computer"></a>Uzak Linux bilgisayarınıza bağlayın

Oluştururken, Linux kod uzak Linux bilgisayarınıza kopyalanan ve ardından Visual Studio'da seçilen ayarlara göre bu sistemde derlenmiş.  Bu uzak bağlantı kurmak için:

1. İlk kez projeyi oluşturun veya yeni bir giriş seçerek el ile oluşturun **Araçlar > Seçenekler** ve ardından açın **Çapraz Platform > Bağlantı Yöneticisi** düğümü ve tıklatın **Ekle** düğmesi.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   Her iki senaryoda **uzak sisteme bağlanma** penceresi görüntülenir.
   
   ![Uzak sisteme bağlanmak](media/connect.png)

1. Aşağıdaki bilgileri girin:

   | Giriş | Açıklama
   | ----- | ---
   | **Ana bilgisayar adı**           | Hedef aygıt adı veya IP adresi
   | **Bağlantı noktası**                | Genellikle, 22 SSH hizmeti çalışıyor bağlantı noktası
   | **Kullanıcı adı**           | Kullanıcı olarak kimlik doğrulaması
   | **Kimlik doğrulama türü** | Parola veya özel anahtar desteklenir
   | **Parola**            | Girilen kullanıcı adı parolası
   | **Özel anahtar dosyası**    | Özel anahtar için ssh bağlantısı oluşturuldu
   | **Parola**          | Yukarıda seçilen özel anahtarla kullanılan parola

1. Tıklatın **Bağlan** uzak bilgisayara bağlanmaya düğmesi.  Bağlantı başarısız olursa, değiştirilmesi gereken giriş kutularının kırmızı renkle gösterilir.

   ![Bağlantı Yöneticisi hata](media/settings_connectionmanagererror.png)