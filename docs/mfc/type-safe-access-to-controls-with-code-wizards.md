---
title: "Kod sihirbazları kullanarak denetimlere tür kullanımı uyumlu erişim | Microsoft Docs"
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
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a431061704bf2affa8a343487ff20f8b55b9e6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim
DDX özelliklerle hakkında bilginiz varsa Denetim özelliğinde kullanabilirsiniz [üye değişkeni ekleme](../ide/add-member-variable-wizard.md) tür kullanımı uyumlu erişim oluşturmak için. Bu yaklaşım, kod sihirbazları olmadan denetimler oluşturmaktan daha kolaydır.  
  
 Yalnızca bir denetimin değerine erişmek istiyorsanız, bunu DDX sağlar. Bir denetimin değerini birden fazla erişmek isterseniz, iletişim sınıfınızı uygun sınıfının üye değişkeni eklemek için üye değişkeni Ekleme Sihirbazı'nı kullanın. Bu üye değişkeni denetim özelliğini ekleyin.  
  
 Üye değişkenleri değer özelliği yerine bir denetim özelliğine sahip olabilir. Value özelliği gibi denetiminden döndürülen veri türünü başvuruyor `CString` veya `int`. Denetim özelliği denetim türü olan denetim sınıfları, MFC'de birini gibi bir veri üyesi aracılığıyla doğrudan erişim sağlayan `CButton` veya `CEdit`.  
  
> [!NOTE]
>  İsterseniz, belirli bir denetim için birden çok üye değişkenleri değer özelliği ve en fazla denetim özelliğine sahip bir üye değişkeni olabilir. Birden çok nesne eklenmiş bir denetim veya başka herhangi bir pencere ileti eşlemesindeki bir belirsizlik olmasına neden olur, çünkü bir denetime eşlenen yalnızca bir MFC nesne olabilir.  
  
 Herhangi bir üye için denetim nesnesi işlevleri çağırmak için bu nesneyi kullanabilirsiniz. Tür çağrılar iletişim kutusunda denetimi etkiler. Örneğin, bir onay kutusu denetimi için bir değişkeni tarafından temsil `m_Checkbox`, türü `CButton`, çağrı:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]  
  
 Burada üye değişkeni `m_Checkbox` üye fonksiyonu aynı amaca hizmet eder `GetMyCheckbox` gösterilen [kod sihirbazları olmadan denetimler için tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-without-code-wizards.md). Onay kutusu bir otomatik onay kutusu yoksa, hala bir işleyici iletişim sınıfınızı gerekir **BN_CLICKED** düğmesine tıklandığında denetim bildirim iletisi.  
  
 Denetimleri hakkında daha fazla bilgi için bkz: [denetimleri](../mfc/controls-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir iletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)   
 [Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-without-code-wizards.md)

