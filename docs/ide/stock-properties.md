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
ms.openlocfilehash: a3586fb33c30148c870b096d0d49a41d7ad8c6c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="stock-properties"></a>Stok Özellikleri
Bir MFC görüntüleme arabirimi kullanarak bir özelliği ekliyorsanız [Özellik Ekleme Sihirbazı'nı](../ide/idl-attributes-add-property-wizard.md), stok özelliğinden seçebilirsiniz **özellik adı** listesinde [adları](../ide/names-add-property-wizard.md) sayfası Sihirbazı. Bu özellikler aşağıdaki gibidir:  
  
|Özellik adı|Açıklama|  
|-------------------|-----------------|  
|**Görünüm**|Döndürür veya denetiminin görünümünü belirleyen bir değer ayarlar. Denetimin **Görünüm** özelliği dahil edebilir veya üç boyutlu görüntü etkileri atlayın. Bu ortam okuma/yazma özelliğidir.|  
|`BackColor`|Döndürür veya denetimin ortam ayarlar `BackColor` özelliği palet (RGB) renk veya önceden tanımlanmış sistem rengi. Varsayılan olarak, denetimin kapsayıcısının ön plan rengini değerini karşılık gelir. Bu ortam okuma/yazma özelliğidir.|  
|`BorderStyle`|Döndürür veya bir denetim kenarlık stilini ayarlar. Bu bir okuma/yazma özelliğidir.|  
|**Açıklamalı alt yazı**|Döndürür veya denetimin ayarlar **resim yazısı** özelliği. Resim yazısını penceresi başlığıdır. **Resim yazısı** hiç **üye değişkeni** uygulama türü.|  
|**Etkin**|Döndürür veya denetimin ayarlar **etkin** özelliği. Etkin bir denetim, kullanıcı tarafından oluşturulan olaylara yanıt verebilir.|  
|**Yazı tipi**|Döndürür veya denetimin ortam yazı tipi ayarlar. Denetim yazı tipi yoksa null.|  
|`ForeColor`|Döndürür veya denetimin ortam ayarlar `ForeColor` özelliği.|  
|**hWnd**|Döndürür veya denetimin ayarlar **hWnd** özelliği. **hWnd** hiç **üye değişkeni** uygulama türü.|  
|**ReadyState**|Döndürür veya denetimin ayarlar **ReadyState** özelliği. Bir denetim başlatılmamış, başlatılmış, yükleme, etkileşimli veya tam olabilir. Bkz: [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx) içinde *Internet SDK* daha fazla bilgi için.|  
|**Metin**|Döndürür veya bir denetiminde bulunan metin ayarlar. **Metin** hiç **üye değişkeni** uygulama türü.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik ekleme](../ide/adding-a-property-visual-cpp.md)   
 [IDL Öznitelikleri, Özellik Ekleme Sihirbazı](../ide/idl-attributes-add-property-wizard.md)