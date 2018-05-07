---
title: Yaygın olarak geçersiz kılınan üye işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed090057394c385dd12825864c5de9ff7d079e29
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="commonly-overridden-member-functions"></a>Yaygın Olarak Geçersiz Kılınan Üye İşlevleri
Aşağıdaki tabloda en olası üye işlevlerini geçersiz kılması listeler, `CDialog`-türetilmiş sınıf.  
  
### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Yaygın olarak geçersiz kılınan üye işlevleri sınıfı CDialog  
  
|Üye işlevi|İçin yanıt iletisi|Geçersiz kılma amacı|  
|---------------------|----------------------------|-----------------------------|  
|`OnInitDialog`|**WM_INITDIALOG**|İletişim kutusunun denetimleri başlatır.|  
|`OnOK`|**BN_CLICKED** düğmesi için **IDOK**|Kullanıcı Tamam düğmesine tıkladığında yanıt verir.|  
|`OnCancel`|**BN_CLICKED** düğmesi için **IDCANCEL**|Kullanıcı iptal düğmesine tıkladığında yanıt verir.|  
  
 `OnInitDialog`, `OnOK`, ve `OnCancel` sanal işlevlerdir. Bunları geçersiz kılmak için bir geçersiz kılma işlevi türetilmiş iletişim sınıfı kullanarak bildirdiğiniz [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
 `OnInitDialog` yalnızca iletişim kutusu görüntülenmeden önce çağrılır. Varsayılan çağırmalısınız `OnInitDialog` geçersiz kılma işleyicisinden — genellikle işleyici ilk eylem olarak. Varsayılan olarak, `OnInitDialog` döndürür **TRUE** odağı iletişim kutusunda ilk denetime ayarlanmalıdır belirtmek için.  
  
 `OnOK` genellikle kalıcı olmayan ancak kalıcı olmayan iletişim kutuları için geçersiz kılındı. Modal bir iletişim kutusu için bu işleyici geçersiz kılarsanız, temel sınıf sürümü geçersiz kılma çağrı — emin olmak için `EndDialog` adlandırılır — veya arama `EndDialog` kendiniz.  
  
 `OnCancel` genellikle kalıcı olmayan iletişim kutuları için geçersiz kılındı.  
  
 Bu üye işlevleri hakkında daha fazla bilgi için bkz [CDialog](../mfc/reference/cdialog-class.md) içinde *MFC başvurusu* ve tartışma [iletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [Yaygın Olarak Eklenen Üye İşlevleri](../mfc/commonly-added-member-functions.md)
