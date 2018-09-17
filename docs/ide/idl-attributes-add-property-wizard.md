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
ms.openlocfilehash: 7da654321dfae520f458374654a21a9e8ebb98f5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706660"
---
# <a name="idl-attributes-add-property-wizard"></a>IDL Öznitelikleri, Özellik Ekleme Sihirbazı
Bir özellik için arabirim tanımlama dili (IDL) ayarlarını belirtmek için bu sayfanın bir özellik Ekleme Sihirbazı'nı kullanın.  
  
- **id**

   Özelliği tanımlayan sayısal bir kimlik ayarlar. Bu seçenek, özel arabirimler özellikleri için kullanılamaz. Bkz: [kimliği](/windows/desktop/Midl/id) içinde *MIDL başvuru*.  
  
- **helpcontext**

   Kullanıcı Yardım dosyasında bu özellik hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir. Bkz: [helpcontext](/windows/desktop/Midl/helpcontext) içinde *MIDL başvuru*.  
  
- **helpstring**

   Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir. Varsayılan olarak ayarlanmış "özelliği *özellik adı*." Bkz: [helpstring](/windows/desktop/Midl/helpstring) içinde *MIDL başvuru*.  
  
## <a name="other-options"></a>Diğer Seçenekler  

Tüm seçenekler için tüm özellik türleri kullanılabilir değildir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**bindable**|Özelliğin veri bağlamayı desteklediğini belirtir. Bkz: [bağlanabilir](/windows/desktop/Midl/bindable) içinde *MIDL başvuru*. Özelliğin stok uygulaması, bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|  
|**defaultbind**|Bunun tek ve bağlanabilir özelliği en iyi temsil ettiğini gösteren nesne. Bkz: [defaultbind](/windows/desktop/Midl/defaultbind) içinde *MIDL başvuru*.|  
|**displaybind**|Bu özellik kullanıcıya bağlanabilir olarak görüntülenmesi gerektiğini gösterir. Bkz: [displaybind](/windows/desktop/Midl/displaybind) içinde *MIDL başvuru*.|  
|**immediatebind**|Veritabanı bu özellik bir veri bağlama nesnesinin yapılan tüm değişikliklerin hemen bildirileceğini belirtir. Bkz: [immediatebind](/windows/desktop/Midl/immediatebind) içinde *MIDL başvuru*.|  
|**defaultcollelem**|Özelliğin varsayılan koleksiyonun bir öğesi için bir erişimci işlevi gösterir. Bkz: [defaultcollelem](/windows/desktop/Midl/defaultcollelem) içinde *MIDL başvuru*.|  
|**nonbrowsable**|Özellikler tarayıcısında görüntülenmemelidir bir arabirim veya dispinterface üye etiketler. Bkz: [nonbrowsable](/windows/desktop/Midl/nonbrowsable) içinde *MIDL başvuru*.|  
|**requestedit**|Özelliğin desteklediğini belirtir **OnRequestEdit** bildirim bakın [requestedit](/windows/desktop/Midl/requestedit) içinde *MIDL başvuru*. Özelliğin stok uygulaması, bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|  
|**Kaynak**|Üye özelliğinin bir olay kaynağı olduğunu gösterir. Bkz: [kaynak](/windows/desktop/Midl/source) içinde *MIDL başvuru*.|  
|**hidden**|Özelliği var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir. Bkz: [gizli](/windows/desktop/Midl/hidden) içinde *MIDL başvuru*.|  
|**restricted**|Özellik rasgele çağrılamaz belirtir. Bkz: [kısıtlı](/windows/desktop/Midl/restricted) içinde *MIDL başvuru*.|  
|`local`|MIDL derleyicisine özelliği uzak olmadığını belirtir. Bkz: [yerel](/windows/desktop/Midl/local) içinde *MIDL başvuru*.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik ekleme](../ide/adding-a-property-visual-cpp.md)   
 [Adlar, Özellik Ekleme Sihirbazı](../ide/names-add-property-wizard.md)   
 [Arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md)   
 [Stok Özellikleri](../ide/stock-properties.md)