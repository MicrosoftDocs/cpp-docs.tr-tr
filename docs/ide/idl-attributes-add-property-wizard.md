---
title: "IDL öznitelikleri, Özellik Ekleme Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.prop.idlattributes
dev_langs: C++
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8dd58ebd25c3b70b10ae3530577d70058bef5b86
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="idl-attributes-add-property-wizard"></a>IDL Öznitelikleri, Özellik Ekleme Sihirbazı
Özelliği arabirimi tanım dili (IDL) ayarlarını belirtmek için bu sayfanın Özellik Ekleme Sihirbazı'nı kullanın.  
  
 **Kimliği**  
 Özelliği tanımlayan sayısal Kimliğini ayarlar. Bu seçenek, özel arabirimleri özellikleri için kullanılamaz. Bkz: [kimliği](http://msdn.microsoft.com/library/windows/desktop/aa367040) içinde *MIDL başvuru*.  
  
 **HelpContext**  
 Yardım dosyasında bu özellik hakkında kullanıcı görünümü bilgi sağlayan bir içerik Kimliğini belirtir. Bkz: [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) içinde *MIDL başvuru*.  
  
 **HelpString**  
 Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir. Varsayılan olarak, bunu ayarlamak "özelliği *özellik adı*." Bkz: [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) içinde *MIDL başvuru*.  
  
## <a name="other-options"></a>Diğer seçenekleri  
 Tüm özellik türleri için tüm seçenekleri kullanılabilir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**bağlanabilir**|Özellik veri bağlama desteklediğini belirtir. Bkz: [bağlanabilirse](http://msdn.microsoft.com/library/windows/desktop/aa366738) içinde *MIDL başvuru*. Özelliğin stok uygulaması, bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|  
|**defaultbind**|Bu en iyi bağlanabilir, tek özellik temsil ettiğini gösterir nesne. Bkz: [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790) içinde *MIDL başvuru*.|  
|**displaybind**|Bu özellik kullanıcıya bağlanabilir olarak görüntüleneceğini gösterir. Bkz: [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804) içinde *MIDL başvuru*.|  
|**immediatebind**|Veritabanı, bu özelliğe bir veri bağlama nesnesinin tüm değişikliklerini hemen bildirilecek gösterir. Bkz: [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045) içinde *MIDL başvuru*.|  
|**defaultcollelem**|Özelliğin varsayılan koleksiyonun bir öğesi için bir erişimci işlevi olduğunu gösterir. Bkz: [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) içinde *MIDL başvuru*.|  
|**nonbrowsable**|Özellikler tarayıcıda görüntülenmemelidir bir arabirim veya görüntüleme arabirimi üye etiketler. Bkz: [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) içinde *MIDL başvuru*.|  
|**requestedit**|Özellik desteklediğini gösterir **OnRequestEdit** bildirim bakın [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155) içinde *MIDL başvuru*. Özelliğin stok uygulaması, bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|  
|**Kaynak**|Bir özellik üyesi olayları kaynağı olduğunu gösterir. Bkz: [kaynak](http://msdn.microsoft.com/library/windows/desktop/aa367166) içinde *MIDL başvuru*.|  
|**Gizli**|Özelliği var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir. Bkz: [gizli](http://msdn.microsoft.com/library/windows/desktop/aa366861) içinde *MIDL başvuru*.|  
|**sınırlı**|Özelliği rasgele çağrılamıyor belirtir. Bkz: [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) içinde *MIDL başvuru*.|  
|`local`|MIDL derleyici özelliği uzak olmadığını belirtir. Bkz: [yerel](http://msdn.microsoft.com/library/windows/desktop/aa367071) içinde *MIDL başvuru*.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik ekleme](../ide/adding-a-property-visual-cpp.md)   
 [Adlar, Özellik Ekleme Sihirbazı](../ide/names-add-property-wizard.md)   
 [Arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md)   
 [Stok özellikleri](../ide/stock-properties.md)