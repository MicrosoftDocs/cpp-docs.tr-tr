---
title: "MFC ActiveX denetimleri: Ortam özelliklerine erişme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b05e6d37a0550cf157dcd43a22689c9db029b51f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC ActiveX Denetimleri: Ortam Özelliklerine Erişme
Bu makalede, bir ActiveX denetimini ortam özelliklerine denetim kapsayıcısının nasıl erişebileceğiniz açıklanır.  
  
 Bir denetim, kapsayıcının ortam özelliklerine erişme tarafından kapsayıcısı hakkında bilgi edinebilirsiniz. Bu özellikler kapsayıcının arka plan rengi, kapsayıcı şu anda kullanıcı modu veya tasarımcı modunda olup gibi kapsayıcı ve işletimsel özellikleri tarafından kullanılan geçerli yazı tipi gibi görsel özelliklerini kullanıma sunar. Bir denetim ortam özelliklerine görünümünü ve davranışını katıştırılmış olan belirli kapsayıcısı uyarlamak için kullanabilirsiniz. Ancak, bir denetim hiçbir zaman kapsayıcısı herhangi belirli bir ortam özelliği destekleyecek varsayın. Aslında, bazı kapsayıcıları tüm ortam özelliklerine hiç desteklemeyebilir. Bir ortam özelliği olmaması durumunda, bir denetim makul varsayılan bir değer varsayın.  
  
 Ortam bir özelliğe erişmek için çağırmaya [COleControl::GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty). Bu işlev, ilk parametre olarak (dosya OLECTL. gönderme kimliği ortam özelliği için bekliyor H gönderme kimliklerinden ortam özelliklerine standart kümesi için tanımlar).  
  
 Parametreleri `GetAmbientProperty` işlevi olduğunu gönderme kimliği, beklenen özellik türü ve bellek için bir işaretçi gösteren bir değişken etiket değeri burada döndürülmelidir. Bu işaretçinin başvurduğu veri türünü değişken etiketi bağlı olarak değişir. İşlevi döndürür **TRUE** kapsayıcı özelliğini destekliyorsa, aksi takdirde döndürür **FALSE**.  
  
 Aşağıdaki kod örneğinde "Kullanıcı modu" adlı ortam özelliği değerini alır Özelliği bir varsayılan değeri kapsayıcı tarafından desteklenmiyor, **TRUE** varsayılır:  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 Size kolaylık sağlamak için `COleControl` özellikler kullanılabilir olmadığında birçok yaygın olarak kullanılan ortam özelliklerine erişme ve uygun varsayılanlara yardımcı işlevleri sağlar. Bu yardımcı işlevleri aşağıdaki gibidir:  
  
-   [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)  
  
-   [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)  
  
-   [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)  
  
    > [!NOTE]
    >  Arayan çağırmalıdır **bırakın ()** döndürülen yazı tipi üzerinde.  
  
-   [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)  
  
-   [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)  
  
-   [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)  
  
-   [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)  
  
-   [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)  
  
-   [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)  
  
-   [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)  
  
-   [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)  
  
 Bir ortam özelliğinin değeri (bazı eylem kapsayıcısının), değişirse **OnAmbientPropertyChanged** denetiminin üye işlevi çağrılır. Böyle bir bildirim işlemek için bu üye işlev geçersiz kılar. Parametresi için **OnAmbientPropertyChanged** etkilenen ortam özelliği gönderme kimliğidir. Bu dağıtım ID değeri olabilir **DISPID_UNKNOWN**, bir veya daha fazla ortam özelliklerine değişti, ancak hangi özellikleri bundan bilgi kullanılamıyor gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

