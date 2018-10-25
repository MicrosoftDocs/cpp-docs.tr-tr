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
ms.openlocfilehash: 387550fa7d3e745038d0be8ee66574d4496132a0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061294"
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