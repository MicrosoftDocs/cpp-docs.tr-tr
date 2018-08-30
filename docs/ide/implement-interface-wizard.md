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
ms.openlocfilehash: c43619fcb1d684d7e0d2d6645b7a5feaac61e472
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195201"
---
# <a name="implement-interface-wizard"></a>Arabirim Uygulama Sihirbazı
Bu sihirbaz bir COM nesnesi için bir arabirim uygular. Pek çok arabirimi uygulamalarını Visual Studio ve Windows ile kullanılabilir COM kitaplıkları dahil edilmiştir. Bir arabirim uygulaması, o nesnenin bir örneği oluşturulduğunda ve nesnenin sunduğu hizmetleri sağlayan bir nesne ile ilişkilidir.  
  
 Arabirimleri ve uygulamalar için bkz [arabirimleri ve arabirim uygulamalarına](/windows/desktop/com/interfaces-and-interface-implementations) Windows SDK.  
  
 **Arabirimi Uygula**  
 Arabirim oluşturulduğu tür kitaplığının konumu belirtir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Project**|Tür kitaplığı projesi bir parçasıdır.|  
|**Kayıt defteri**|Tür kitaplığını sistemde kayıtlı. Kayıtlı bir tür kitaplığı içinde listelenen **kullanılabilir tür kitaplıklarını**.|  
|**Dosya**|Tür kitaplığını mutlaka sistemde kayıtlı değil ancak bir dosyada yer alır. Dosya konumunda sağlamalısınız **konumu**.|  
  
 **Kullanılabilir tür kitaplıkları**  
 Uygulayabileceğiniz arabirim tanımlarını içeren kullanılabilir tür kitaplıklarını görüntüler. Tıklarsanız **dosya** altında **uygulama arabiriminden**, bu kutusuna değişiklik için kullanılamıyor.  
  
 **Konum**  
 Şu anda seçilen tür kitaplığının konumu görüntüler **kullanılabilir tür kitaplıklarını** listesi. Seçtiyseniz **dosya** altında **uygulama arabiriminden**, tür kitaplığı içeren bir dosyayı bulmak için üç nokta düğmesine tıklayın.  
  
 **Arabirimler**  
 Görüntüler, tanımları, şu anda seçili tür kitaplığı içerdiği arabirimleri **kullanılabilir tür kitaplıklarını** kutusu.  
  
> [!NOTE]
>  Bu seçilen nesne tarafından zaten uygulanmış gösterilmez gibi aynı ada sahip arabirimler **arabirimleri** kutusu.  
  
|Aktarım düğmesi|Açıklama|  
|---------------------|-----------------|  
|**>**|Ekler **arabirimleri uygulayan** geçerli seçili arabirim adı listesi **arabirimleri** listesi.|  
|**>>**|Ekler **arabirimleri uygulayan** bulunan tüm arabirimi adlarını listelemek **arabirimleri** listesi.|  
|**<**|Şu anda seçili arabirim adını kaldırır **arabirimleri uygulayan** listesi.|  
|**<\<**|Şu anda listelenen adları tüm arabirim kaldırır **arabirimleri uygulayan** listesi.|  
  
 **Arabirimi uygulayan**  
 Nesneniz üzerinde uygulamak için seçtiğiniz arabirimleri adlarını görüntüler.  
  
> [!NOTE]
>  Öğesinden türetilen birden fazla arabirim içerip içermediğini `IDispatch`, veya sınıfınıza üzerinde zaten başka bir arabirimden türetilmiş bir arabirim uygulamak deneyin ardından COM_MAP girişlerin ayırt etmek gerekir. Bkz: [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md)