---
title: Visual Studio'da uzak Linux bilgisayarınıza bağlayın | Microsoft Docs
description: Visual Studio C++ projesi içinde uzak Linux makineden bağlanma.
ms.custom: ''
ms.date: 07/20/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 5e6a5dd4a00bd4d98c36222434d7cd83242905c9
ms.sourcegitcommit: db6b2ad3195e71abfb60b62f3f015f08b0a719d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410765"
---
# <a name="connect-to-your-remote-linux-computer"></a>Uzak Linux bilgisayarınıza bağlanma

Visual Studio'da C++ Linux projesi oluştururken, kodu uzak Linux bilgisayarınıza kopyalanır ve sonra derlenmiş Linux Visual Studio ayarlarınızı temel alan. Bu uzak bağlantı kurmak için:

1. İlk kez projeyi derlemeyi ya da el ile seçerek yeni bir giriş oluşturun **Araçlar > Seçenekler** ve açın **Çoklu Platform > Bağlantı Yöneticisi** düğüm ve tıklatın **Ekle** düğmesi.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   Her iki senaryoda **uzak sisteme Bağlan** penceresi görüntülenir.
   
   ![Uzak sisteme Bağlan](media/connect.png)

1. Aşağıdaki bilgileri girin:

   | Giriş | Açıklama
   | ----- | ---
   | **Ana bilgisayar adı**           | Hedef cihazınızın adı veya IP adresi
   | **Bağlantı noktası**                | Genellikle, 22 SSH hizmeti çalışıyor bağlantı noktası
   | **Kullanıcı adı**           | Kullanıcı olarak kimlik doğrulaması yapmak için
   | **Kimlik doğrulaması türü** | Parola veya özel anahtar desteklenir
   | **Parola**            | Girilen kullanıcı adının parolası
   | **Özel anahtar dosyası**    | Özel anahtar dosyası için ssh bağlantı oluşturuldu
   | **Parola**          | Yukarıda seçilen özel anahtarlı kullanılan parola

1. Tıklayın **Connect** uzak bilgisayara bağlanmaya düğmesi.  Değiştirilmesi gereken giriş kutularının bağlantı başarısız olursa, kırmızı renkle gösterilir.

   ![Bağlantı Yöneticisi hata](media/settings_connectionmanagererror.png)