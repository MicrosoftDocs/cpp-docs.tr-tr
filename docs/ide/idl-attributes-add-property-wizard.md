---
title: IDL öznitelikleri, Özellik Ekleme Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.prop.idlattributes
dev_langs:
- C++
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77931296d8d33337c4e630b7327a1ec8fd0a458f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33340196"
---
# <a name="idl-attributes-add-property-wizard"></a>IDL Öznitelikleri, Özellik Ekleme Sihirbazı
Özelliği arabirimi tanım dili (IDL) ayarlarını belirtmek için bu sayfanın Özellik Ekleme Sihirbazı'nı kullanın.  
  
 **id**  
 Özelliği tanımlayan sayısal Kimliğini ayarlar. Bu seçenek, özel arabirimleri özellikleri için kullanılamaz. Bkz: [kimliği](http://msdn.microsoft.com/library/windows/desktop/aa367040) içinde *MIDL başvuru*.  
  
 **helpcontext**  
 Yardım dosyasında bu özellik hakkında kullanıcı görünümü bilgi sağlayan bir içerik Kimliğini belirtir. Bkz: [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) içinde *MIDL başvuru*.  
  
 **helpstring**  
 Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir. Varsayılan olarak, bunu ayarlamak "özelliği *özellik adı*." Bkz: [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) içinde *MIDL başvuru*.  
  
## <a name="other-options"></a>Diğer seçenekleri  
 Tüm özellik türleri için tüm seçenekleri kullanılabilir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**bindable**|Özellik veri bağlama desteklediğini belirtir. Bkz: [bağlanabilirse](http://msdn.microsoft.com/library/windows/desktop/aa366738) içinde *MIDL başvuru*. Özelliğin stok uygulaması, bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|  
|**defaultbind**|Bu en iyi bağlanabilir, tek özellik temsil ettiğini gösterir nesne. Bkz: [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790) içinde *MIDL başvuru*.|  
|**displaybind**|Bu özellik kullanıcıya bağlanabilir olarak görüntüleneceğini gösterir. Bkz: [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804) içinde *MIDL başvuru*.|  
|**immediatebind**|Veritabanı, bu özelliğe bir veri bağlama nesnesinin tüm değişikliklerini hemen bildirilecek gösterir. Bkz: [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045) içinde *MIDL başvuru*.|  
|**defaultcollelem**|Özelliğin varsayılan koleksiyonun bir öğesi için bir erişimci işlevi olduğunu gösterir. Bkz: [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) içinde *MIDL başvuru*.|  
|**nonbrowsable**|Özellikler tarayıcıda görüntülenmemelidir bir arabirim veya görüntüleme arabirimi üye etiketler. Bkz: [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) içinde *MIDL başvuru*.|  
|**requestedit**|Özellik desteklediğini gösterir **OnRequestEdit** bildirim bakın [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155) içinde *MIDL başvuru*. Özelliğin stok uygulaması, bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|  
|**Kaynak**|Bir özellik üyesi olayları kaynağı olduğunu gösterir. Bkz: [kaynak](http://msdn.microsoft.com/library/windows/desktop/aa367166) içinde *MIDL başvuru*.|  
|**hidden**|Özelliği var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir. Bkz: [gizli](http://msdn.microsoft.com/library/windows/desktop/aa366861) içinde *MIDL başvuru*.|  
|**restricted**|Özelliği rasgele çağrılamıyor belirtir. Bkz: [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) içinde *MIDL başvuru*.|  
|`local`|MIDL derleyici özelliği uzak olmadığını belirtir. Bkz: [yerel](http://msdn.microsoft.com/library/windows/desktop/aa367071) içinde *MIDL başvuru*.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik ekleme](../ide/adding-a-property-visual-cpp.md)   
 [Adlar, Özellik Ekleme Sihirbazı](../ide/names-add-property-wizard.md)   
 [Arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md)   
 [Stok Özellikleri](../ide/stock-properties.md)