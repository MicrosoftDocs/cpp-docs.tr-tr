---
title: Yaygın Olarak Geçersiz Kılınan Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
ms.openlocfilehash: 163da1ee6e98e974af0fd1a6b27e1b2df85e9ce0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439601"
---
# <a name="commonly-overridden-member-functions"></a>Yaygın Olarak Geçersiz Kılınan Üye İşlevleri

Aşağıdaki tablo en olası içinde geçersiz kılmak için üye işlevleri listeler, `CDialog`-türetilmiş sınıf.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Yaygın olarak geçersiz kılınan üye işlevleri, CDialog sınıfı

|Üye işlevi|Bu yanıt iletisi|Geçersiz kılma amacı|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|İletişim kutusunun denetimleri başlatılamıyor.|
|`OnOK`|**BN_CLICKED** düğmesi **IDOK**|Kullanıcı Tamam düğmesine tıkladığında yanıt.|
|`OnCancel`|**BN_CLICKED** düğmesi **IDCANCEL**|Kullanıcı iptal düğmesine tıkladığında yanıt.|

`OnInitDialog`, `OnOK`, ve `OnCancel` sanal işlev. Bunları geçersiz kılmak için bir geçersiz kılma işlevi kullanarak, iletişim türetilmiş sınıftaki bildirmeniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

`OnInitDialog` Yeni iletişim kutusu görüntülenmeden önce çağrılır. Varsayılan çağırmalıdır `OnInitDialog` geçersiz kılma işleyicisinden — genellikle işleyici ilk eylem olarak. Varsayılan olarak, `OnInitDialog` döndürür **TRUE** odağı iletişim kutusunda ilk denetimine ayarlanmalıdır belirtmek için.

`OnOK` kalıcı olmayan ancak kalıcı olmayan iletişim kutuları için genellikle geçersiz kılınır. Bu işleyici kalıcı bir iletişim kutusu için geçersiz kılarsanız, temel sınıftaki sürümün geçersiz kılma çağrı — emin olmak için `EndDialog` adlandırılır — veya çağrı `EndDialog` kendiniz.

`OnCancel` kalıcı olmayan iletişim kutuları için genellikle geçersiz kılınır.

Bu üye işlevleri hakkında daha fazla bilgi için bkz. [CDialog](../mfc/reference/cdialog-class.md) içinde *MFC başvurusu* ve tartışma [iletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md).

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Yaygın Olarak Eklenen Üye İşlevleri](../mfc/commonly-added-member-functions.md)
