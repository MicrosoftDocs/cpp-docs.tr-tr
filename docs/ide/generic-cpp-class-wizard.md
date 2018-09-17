---
title: Genel C++ sınıfı Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.class.generic
dev_langs:
- C++
helpviewer_keywords:
- Generic C++ Class Wizard [C++]
ms.assetid: aa95be9e-fc1b-45db-a11d-0d32c4929077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 758aafa91a8b74c52e8af88e0f6862c1cf99f229
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719627"
---
# <a name="generic-c-class-wizard"></a>Genel C++ Sınıfı Sihirbazı

Projeye Genel C++ sınıfı ekler. Sınıfı, ATL veya MFC devralmaz.  
  
- **Sınıf adı**

   Yeni bir sınıf adını ayarlar.  
  
- **.h dosyası**

   Yeni bir sınıf için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıf adı**. Üst bilgi dosyası istediğiniz konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini (**...** ). ' A tıkladığınızda, var olan bir dosya belirtirseniz **son**, sihirbaz sınıf bildirimi dosya içeriğini eklenmeyeceğini belirtmenizi ister. Bildirimi eklemek için tıklatın **Evet**; sihirbaza dönmek ve başka bir dosya adı belirtin, tıklatın **Hayır**.  
  
- **.cpp dosyası**

   Yeni bir sınıf için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıf adı**. Uygulama dosyası istediğiniz konuma kaydedin veya mevcut bir dosyaya sınıf tanımı eklemek için üç nokta düğmesini (**...** ). ' A tıkladığınızda, var olan bir dosya belirtirseniz **son**, sihirbaz sınıf tanımının dosyasının içeriğini eklenmeyeceğini belirtmenizi ister. Tanımı eklemek için tıklatın **Evet**; sihirbaza dönmek ve başka bir dosya adı belirtin, tıklatın **Hayır**.  
  
- **Temel sınıf**

   Yeni bir sınıf için taban sınıf ayarlar.  
  
- **Erişim**

   Yeni bir sınıf için taban sınıf üyelerine erişimi ayarlar. Erişim değiştiricileri diğer sınıflara sahip sınıf üyesi işlevleri için erişim düzeyini belirten anahtar sözcüklerdir. Erişim belirtme hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md). Varsayılan olarak, sınıf erişim düzeyini ayarlamak `public`.  
  
   - `public`  
  
   - `protected`  
  
   - `private`  
  
   - **Varsayılan** (herhangi bir erişim değiştiricisi oluşturulur.)  
  
- **Sanal yıkıcı**

   Sınıf yok edicisini sanal olup olmadığını belirtir. Sanal bir yıkıcı kullanılmasını, özel olarak türetilmiş sınıfların örneklerini silindiğinde doğru yok Edicisi çağrılır sağlamaya yardımcı olur.  
  
- **Satır içi**

   Üstbilgi dosyasında, sınıf oluşturucusu hem satır içi işlevleri olarak sınıf tanımı oluşturur.  
  
- **Yönetilen**

   Bu onay kutusu seçildiğinde, yönetilen bir sınıf ve üstbilgi dosyası ekler. Bu onay kutusu temizlenirse, yerel bir sınıf ve üstbilgi dosyası ekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel C++ Sınıfı Ekleme](../ide/adding-a-generic-cpp-class.md)