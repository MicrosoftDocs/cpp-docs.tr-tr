---
title: "Standart bir denetimden denetim türetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b93bc07fc5ab4680caaa276daaeca86189b8ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="deriving-controls-from-a-standard-control"></a>Standart Bir Denetimden Denetim Türetme
Herhangi bir olduğu gibi [CWnd](../mfc/reference/cwnd-class.md)-türetilmiş sınıf, var olan bir denetim sınıfından yeni bir sınıf türetme tarafından bir denetimin davranışı değiştirebilirsiniz.  
  
### <a name="to-create-a-derived-control-class"></a>Bir türetilmiş denetim sınıfı oluşturmak için  
  
1.  Sınıfınızda var olan bir denetim sınıfından türetilen ve isteğe bağlı olarak geçersiz kılma **oluşturma** üye gördüğünü gerekli bağımsız değişkenler için temel sınıf sağlar **oluşturma** işlevi.  
  
2.  İleti işleyicisi üye işlevleri ve belirli Windows iletilere yanıt olarak denetimin davranışını değiştirmek için ileti eşlemesi girişleri sağlar. Bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).  
  
3.  (İsteğe bağlı) denetim işlevselliğini genişletmek için yeni üye işlevleri sağlar.  
  
 Türetilen bir denetim bir iletişim kutusunu kullanarak ek iş gerektirir. Normalde türleri ve bir iletişim kutusu denetimleri konumda bir iletişim şablonunu kaynak olarak belirtilir. Bir türetilmiş denetim sınıfı oluşturursanız, kaynak derleyici, türetilmiş bir sınıf hakkında hiçbir şey bilmez olduğundan, bir iletişim şablonunu belirtemezsiniz.  
  
#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>Bir iletişim kutusunda, türetilmiş denetim yerleştirmek için  
  
1.  Türetilmiş denetim sınıfın bir nesnesi türetilmiş iletişim sınıfınızı bildiriminde ekleyin.  
  
2.  Geçersiz kılma `OnInitDialog` üye işlevi çağırmak için iletişim sınıfınızda `SubclassDlgItem` üye işlevi türetilmiş denetim için.  
  
 `SubclassDlgItem`"dinamik olarak alt sınıfların" bir denetim bir iletişim kutusu şablondan oluşturuldu. Denetim dinamik olarak oluşturulduğunda, pencerelere kanca, kendi uygulama içinde bazı iletileri işlemek ve sonra Windows kalan iletileri geçirin. Daha fazla bilgi için bkz: [SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem) sınıfının üye işlevini `CWnd` içinde *MFC başvurusu*. Aşağıdaki örnek, bir geçersiz kılma nasıl yazabilir gösterir `OnInitDialog` çağırmak için `SubclassDlgItem`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]  
  
 Türetilmiş denetim iletişim kutusu sınıfında gömülü olduğundan iletişim kutusu oluşturulur ve iletişim kutusunu bozulduğunda yok edilir oluşturulur. Bu örnekte kodla karşılaştırın [ekleme denetimlerini By el](../mfc/adding-controls-by-hand.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)   
 [Denetimler](../mfc/controls-mfc.md)

