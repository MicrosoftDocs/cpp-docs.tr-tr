---
title: Stok özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- stock properties, about stock properties
- stock properties
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a9b2aa4389d693cfc6734a29f3a744e955ca3ea
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213799"
---
# <a name="stock-properties"></a>Stok Özellikleri
Bir MFC dispinterface kullanarak bir özelliği ekliyorsanız [Özellik Ekleme Sihirbazı'nı](../ide/idl-attributes-add-property-wizard.md), stok özelliğinden seçebilirsiniz **özellik adı** listesinde [adları](../ide/names-add-property-wizard.md) sayfası Sihirbaz. Bu özellikler aşağıdaki gibidir:  
  
|Özellik adı|Açıklama|  
|-------------------|-----------------|  
|**Görünüm**|Döndürür veya denetimin görünümünü belirleyen değeri ayarlar. Denetimin **Görünüm** özelliği dahil edebilir veya üç boyutlu görüntü etkileri atlayın. Bu ortam okuma/yazma özelliğidir.|  
|`BackColor`|Döndürür veya denetimin ortam ayarlar `BackColor` özelliği bir palet (RGB) renk ya da önceden tanımlanmış sistem rengi. Varsayılan olarak, denetimin kapsayıcı ön plan rengini değerine karşılık gelir. Bu ortam okuma/yazma özelliğidir.|  
|`BorderStyle`|Döndürür veya bir denetimin kenarlık stilini ayarlar. Bu bir okuma/yazma özelliğidir.|  
|**Resim yazısı**|Döndürür veya denetimin ayarlar **açıklamalı alt yazı** özelliği. Pencerenin başlığı başlıktır. **Açıklamalı alt yazı** hiçbir **üye değişkeni** uygulama türü.|  
|**Etkin**|Döndürür veya denetimin ayarlar **etkin** özelliği. Etkin bir denetim, kullanıcı tarafından oluşturulan olaylara yanıt verebilir.|  
|**Yazı tipi**|Döndürür veya denetimin ortam yazı tipini ayarlar. Denetim yazı tipi yoksa null değeri.|  
|`ForeColor`|Döndürür veya denetimin ortam ayarlar `ForeColor` özelliği.|  
|**hWnd**|Döndürür veya denetimin ayarlar **hWnd** özelliği. **hWnd** hiçbir **üye değişkeni** uygulama türü.|  
|**ReadyState**|Döndürür veya denetimin ayarlar **ReadyState** özelliği. Bir denetim başlatılmamış, başlatılmış, yükleme, etkileşimli veya tam olabilir. Bkz: [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx) içinde *Internet SDK* daha fazla bilgi için.|  
|**Metin**|Döndürür veya bir denetimde bulunan metni ayarlar. **Metin** hiçbir **üye değişkeni** uygulama türü.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik ekleme](../ide/adding-a-property-visual-cpp.md)   
 [IDL Öznitelikleri, Özellik Ekleme Sihirbazı](../ide/idl-attributes-add-property-wizard.md)