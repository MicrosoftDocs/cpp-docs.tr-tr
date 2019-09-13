---
title: Yaygın Olarak Geçersiz Kılınan Üye İşlevleri
ms.date: 09/06/2019
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
ms.openlocfilehash: f63dd6079b96181305f3207d4a1ef823df8d8ba4
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907684"
---
# <a name="commonly-overridden-member-functions"></a>Yaygın Olarak Geçersiz Kılınan Üye İşlevleri

Aşağıdaki tabloda, türetilmiş sınıfınıza `CDialog`geçersiz kılmak için en olası üye işlevleri listelenmektedir.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>CDialog sınıfının genellikle geçersiz kılınan üye Işlevleri

|Üye işlevi|Yanıt verdiği ileti|Geçersiz kılmanın amacı|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|İletişim kutusu denetimlerini başlatın.|
|`OnOK`|Düğme **IDOK** için **BN_CLICKED**|Kullanıcı Tamam düğmesine tıkladığında yanıt verir.|
|`OnCancel`|Düğme **IDCANCEL** için **BN_CLICKED**|Kullanıcı Iptal düğmesine tıkladığında yanıt verir.|

`OnInitDialog`, `OnOK` ve`OnCancel` sanal işlevlerdir. Bunları geçersiz kılmak için, [MFC sınıf Sihirbazı 'nı](reference/mfc-class-wizard.md)kullanarak türetilmiş iletişim sınıfınızda bir geçersiz kılma işlevi bildirirsiniz.

`OnInitDialog`iletişim kutusu görüntülenmeden hemen önce çağrılır. Varsayılan `OnInitDialog` işleyiciyi, genellikle işleyicisindeki ilk eylem olarak, geçersiz kılmanızda çağırmanız gerekir. Varsayılan olarak, `OnInitDialog` odağın iletişim kutusunda ilk denetime ayarlanması gerektiğini belirtmek için **true** değerini döndürür.

`OnOK`genellikle modsuz ancak kalıcı olmayan iletişim kutuları için geçersiz kılınır. Kalıcı bir iletişim kutusu için bu işleyiciyi geçersiz kılarsınız, çağrıldığından emin `EndDialog` olmak için, geçersiz kılmanızda temel sınıf sürümünü çağırın — veya kendi kendinize çağrı `EndDialog` yapın.

`OnCancel`genellikle kalıcı olmayan iletişim kutuları için geçersiz kılınır.

Bu üye işlevleri hakkında daha fazla bilgi için bkz. *MFC başvurusu* Içindeki sınıf [CDialog](../mfc/reference/cdialog-class.md) ve [bir iletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)hakkındaki tartışma.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Yaygın Olarak Eklenen Üye İşlevleri](../mfc/commonly-added-member-functions.md)
