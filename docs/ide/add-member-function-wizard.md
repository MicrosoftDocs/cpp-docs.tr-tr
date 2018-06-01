---
title: Üye işlevi Ekleme Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.function.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Function Wizard [C++]
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 488c7ca455b267a79b0d2906849596346a191792
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33332403"
---
# <a name="add-member-function-wizard"></a>Üye İşlevi Ekleme Sihirbazı
Bu sihirbaz bir üye işlevi bildirimi üstbilgi dosyası ve bir saplama üye işlevi uygulama seçilen sınıf için uygulama dosyasına ekler.  
  
 Sihirbazı'nı kullanarak üye işlevi ekledikten sonra geliştirme ortamı kodda düzenleyebilirsiniz.  
  
 **Dönüş türü**  
 Eklediğiniz üye işlevi için dönüş türünü ayarlar. Kendi dönüş türü sağlayabilir veya kullanılabilir türler listesinden seçebilirsiniz. Türleri hakkında daha fazla bilgi için bkz: [temel türleri](../cpp/fundamental-types-cpp.md).  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **İşlev adı**  
 Eklediğiniz üye işlevin adını ayarlar.  
  
 **Parametre türü**  
 Üye işlevini parametrelere sahipse eklediğiniz üye işlevi için parametre türünü ayarlar. Kendi parametre türü sağlayabilir veya kullanılabilir türler listesinden seçebilirsiniz.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **Parametre adı**  
 Üye işlevini parametrelere sahipse üye fonksiyonu için eklemekte olduğunuz bir parametre adını ayarlar.  
  
 **Parametre listesi**  
 Üye işlevini eklediğiniz parametrelerin listesini görüntüler. Bir parametre listesine eklemek için bir türü sağlayın ve içinde ad **parametre türü** ve **parametre adı** kutuları ve tıklatın **Ekle**. Parametreyi listeden kaldırmak için parametre seçin ve tıklatın **kaldırmak**.  
  
 **Erişim**  
 Erişim için üye işlevi ayarlar. Erişim değiştiricileri diğer sınıflar üye işlevine sahip oldukları erişim belirttiğiniz anahtar sözcükler. Bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md) erişim belirtme hakkında daha fazla bilgi için. Üye işlevi erişim düzeyini ayarlamak **ortak** varsayılan olarak.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 Yeni üye işlevi statik veya sanal olmasına ve satır içi olup denetleyin veya saf. Saf, olması için üye işlevini ayarlarsanız `Virtual` onay kutusu seçilidir ve **satır içi** onay kutusunu kullanılamaz olur. Statik olmayan, sanal olmayan üye işlevi varsayılandır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|[Static](../cpp/storage-classes-cpp.md)|İşlev genel gibi davranır ve sınıfı, hatta sınıfı örneklemesi dışında adlı belirtir. Üye işlevi erişim statik olmayan üye yok. Olarak belirtilen üye işlevi `Static` sanal olamaz.|  
|[Sanal](../cpp/virtual-cpp.md)|Üye işlev çağrısı yapmak için kullanılan ifade bağımsız olarak bir nesne için doğru üye işlevi çağrılır sağlar. Olarak belirtilen üye işlevi `Virtual` statik olamaz.|  
|**Saf**|Hiçbir uygulama bildirilen sanal üye işlevi için sağlanan gösterir; Bu nedenle, **saf** yalnızca sanal üye işlevlerini belirtilebilir. En az bir saf sanal üye işlevi içeren bir sınıf, soyut bir sınıf olarak kabul edilir. Soyut sınıftan türetilen sınıflara saf sanal üye fonksiyonu uygulamalıdır ya da, çok, soyut sınıflar.|  
|[Satır içi](../cpp/inline-functions-cpp.md)|Üye işlev gövdesi bir kopyasını üye fonksiyonu olarak adlandırılan her yerde eklemek için derleyicisi bildirir. Olarak belirtilen üye işlevi **satır içi** saf olamaz.|  
  
 **.cpp dosyası**  
 Saplama üye fonksiyonu uygulama yazıldığı dosya konumunu ayarlar. Varsayılan olarak, üye fonksiyonu ekleneceği sınıfı için .cpp dosyasına yazılır. Dosya adını değiştirmek için üç nokta düğmesini tıklatın. Üye işlev uygulama, seçilen dosya içeriğini eklenir.  
  
 **Yorum**  
 Üye işlevini üstbilgi dosyası bir açıklama sağlar.  
  
 **İşlev imzası**  
 Üye işlevi tıkladığınızda kodda göründüğü gibi görüntüler **son**. Bu kutudaki metnin düzenleyemezsiniz. Üye işlevini değiştirmek için sihirbazın uygun kutulara değiştirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)