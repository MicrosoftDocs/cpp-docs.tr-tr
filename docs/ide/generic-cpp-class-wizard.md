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
ms.openlocfilehash: 43e86a4047ef025f49dd01eda90f324623a90752
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33328311"
---
# <a name="generic-c-class-wizard"></a>Genel C++ Sınıfı Sihirbazı
Genel C++ sınıfı bir projeye ekler. ATL ya da MFC sınıfı devralmaz.  
  
 **Sınıf adı**  
 Yeni sınıf adını ayarlar.  
  
 **.h dosyası**  
 Üst bilgi dosyasını yeni sınıfın adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **sınıf adı**. Üst bilgi dosyasını tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın (**...** ). ' I tıklattığınızda varolan bir dosyanın belirtirseniz **son**, sihirbazın sınıfı bildirim dosyasının içeriğini eklenmiş olup olmadığını belirtmenizi ister. Bildirim eklemek için tıklatın **Evet**; sihirbaza geri dönmek ve başka bir dosya adı belirtin, tıklatın **Hayır**.  
  
 **.cpp dosyası**  
 Yeni sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **sınıf adı**. Uygulama dosyasını tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf tanımını eklemek için üç nokta düğmesini tıklatın (**...** ). ' I tıklattığınızda varolan bir dosyanın belirtirseniz **son**, sihirbazın sınıf tanımını dosyasının içeriğini eklenmiş olup olmadığını belirtmenizi ister. Tanımı eklemek için tıklatın **Evet**; sihirbaza geri dönmek ve başka bir dosya adı belirtin, tıklatın **Hayır**.  
  
 **Taban sınıfı**  
 Yeni sınıf için temel sınıf olarak ayarlar.  
  
 **Erişim**  
 Yeni sınıf için temel sınıf üyelerine erişimi ayarlar. Erişim değiştiricileri sınıf üyesi işlevleri için diğer sınıflara sahip erişim düzeyini belirten anahtar sözcükler. Erişim belirtme hakkında daha fazla bilgi için bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md). Varsayılan olarak, sınıf erişim düzeyini ayarlamak `public`.  
  
-   `public`  
  
-   `protected`  
  
-   `private`  
  
-   **Varsayılan** (herhangi bir erişim değiştiricisi oluşturulur.)  
  
 **Sanal yok Edicisi**  
 Sınıf yıkıcı sanal olup olmadığını belirtir. Bir sanal yıkıcı kullanımını türetilen sınıfların örneklerini silindiğinde, doğru yıkıcı adlı sağlamaya yardımcı olur.  
  
 **Satır içi**  
 Sınıf oluşturucu ve satır içi işlev olarak sınıf tanımını üstbilgi dosyasında oluşturur.  
  
 **Yönetilen**  
 Seçili olduğunda, bir yönetilen sınıf ve üstbilgi dosyası ekler. Bu onay kutusu temizlendiğinde, yerel bir sınıf ve üstbilgi dosyası ekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel C++ Sınıfı Ekleme](../ide/adding-a-generic-cpp-class.md)