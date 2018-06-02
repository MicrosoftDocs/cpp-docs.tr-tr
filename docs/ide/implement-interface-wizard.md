---
title: Uygulama Arabirimi Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.impl.interface.overview
dev_langs:
- C++
helpviewer_keywords:
- Implement Interface Wizard [C++]
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf2ddf83b7a03f8d4e01b61f82e46e0d26a5547b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33340547"
---
# <a name="implement-interface-wizard"></a>Arabirim Uygulama Sihirbazı
Bu sihirbaz bir COM nesnesi için bir arabirimi uygular. Birçok arabirimleri uygulamalarını Visual Studio ve Windows ile kullanılabilir COM kitaplıkları dahil edilmiştir. Söz konusu nesne örneği oluşturulduğunda ve nesne sunar hizmetleri sağlayan bir arabirim uygulamasına sahip bir nesne ilişkilidir.  
  
 Arabirimleri ve uygulamaları tartışma için bkz [arabirimleri ve arabirim uygulamaları](http://msdn.microsoft.com/library/windows/desktop/ms694356) Windows SDK.  
  
 **Uygulama arabirimi**  
 Arabirim oluşturulduğu tür kitaplığı konumunu belirtir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Project**|Tür kitaplığı projesinin bir parçasıdır.|  
|**Kayıt defteri**|Tür kitaplığı sistemde kayıtlı değil. Kayıtlı tür kitaplıklarına içinde listelenen **kullanılabilir tür kitaplıklarının**.|  
|**Dosya**|Tür kitaplığı mutlaka sistemde kayıtlı değil ancak bir dosyada yer alan. Dosya konumu sağlamalısınız **konumu**.|  
  
 **Kullanılabilir tür kitaplıkları**  
 Uygulayabileceğiniz arabirimi tanımlarını içeren kullanılabilir tür kitaplıklarını görüntüler. Tıklatırsanız **dosya** altında **uygulama arabiriminden**, bu kutu değişikliği için kullanılamıyor.  
  
 **Konum**  
 Şu anda seçili tür kitaplığı konumunu görüntüler **kullanılabilir tür kitaplıklarının** listesi. Seçtiyseniz **dosya** altında **uygulama arabiriminden**, kullanmak için tür kitaplığı içeren bir dosyayı bulmak için üç nokta düğmesini tıklatın.  
  
 **Arabirimler**  
 Tanımları, şu anda seçili tür kitaplığı içerdiği arabirimleri görüntüler **kullanılabilir tür kitaplıklarının** kutusu.  
  
> [!NOTE]
>  Bu seçilen nesnesi tarafından zaten uygulanmış gösterilmez gibi aynı ada sahip arabirimleri **arabirimleri** kutusu.  
  
|Aktarma düğmesi|Açıklama|  
|---------------------|-----------------|  
|**>**|Ekler **uygulamak arabirimleri** geçerli seçili arabirim adı listesi **arabirimleri** listesi.|  
|**>>**|Ekler **uygulamak arabirimleri** bulunan tüm arabirim adlarını listelemek **arabirimleri** listesi.|  
|**<**|Şu anda seçili arabirim adı kaldırır **uygulamak arabirimleri** listesi.|  
|**<\<**|Tüm arabirim şu anda listelenen adları kaldırır **uygulamak arabirimleri** listesi.|  
  
 **Arabirimler uygulama**  
 Nesne üzerinde uygulamak için seçtiğiniz arabirimleri adlarını görüntüler.  
  
> [!NOTE]
>  Öğesinden türetilen birden fazla arabirimi içerip içermediğini `IDispatch`, veya başka bir arabirimde zaten sınıfınız türetilir bir arabirim deneyin sonra COM_MAP girişleri belirsizliğini ortadan kaldırmak gerekir. Bkz: [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md)