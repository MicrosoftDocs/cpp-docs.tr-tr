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
ms.openlocfilehash: 51a647bb50415af71d6d148d3139f906f503ee2a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685813"
---
# <a name="commonly-overridden-member-functions"></a>Yaygın Olarak Geçersiz Kılınan Üye İşlevleri

Aşağıdaki tabloda, `CDialog`türetilmiş sınıfınıza geçersiz kılmak için en olası üye işlevleri listelenmektedir.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>CDialog sınıfının genellikle geçersiz kılınan üye Işlevleri

|Üye işlevi|Yanıt verdiği ileti|Geçersiz kılmanın amacı|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|İletişim kutusu denetimlerini başlatın.|
|`OnOK`|Düğme **IDOK** için **BN_CLICKED**|Kullanıcı Tamam düğmesine tıkladığında yanıt verir.|
|`OnCancel`|Düğme **IDCANCEL** için **BN_CLICKED**|Kullanıcı Iptal düğmesine tıkladığında yanıt verir.|

`OnInitDialog`, `OnOK`ve `OnCancel` sanal işlevlerdir. Bunları geçersiz kılmak için, [MFC sınıf Sihirbazı 'nı](reference/mfc-class-wizard.md)kullanarak türetilmiş iletişim sınıfınızda bir geçersiz kılma işlevi bildirirsiniz.

`OnInitDialog`, iletişim kutusu görüntülenmeden hemen önce çağrılır. Varsayılan `OnInitDialog` işleyicisini, genellikle işleyicisindeki ilk eylem olarak, geçersiz kılmanızda çağırmanız gerekir. Varsayılan olarak, `OnInitDialog`, odağın iletişim kutusundaki ilk denetime ayarlanması gerektiğini belirtmek için **true** değerini döndürür.

`OnOK` genellikle modsuz ancak kalıcı olmayan iletişim kutuları için geçersiz kılınır. Kalıcı bir iletişim kutusu için bu işleyiciyi geçersiz kılarsınız, `EndDialog` çağrıldığından emin olmak için, geçersiz kılmanızda temel sınıf sürümünü çağırın — veya `EndDialog` kendiniz çağırın.

`OnCancel` genellikle kalıcı olmayan iletişim kutuları için geçersiz kılınır.

Bu üye işlevleri hakkında daha fazla bilgi için bkz. *MFC başvurusu* Içindeki sınıf [CDialog](../mfc/reference/cdialog-class.md) ve [MFC 'deki iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)hakkında tartışma.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Yaygın Olarak Eklenen Üye İşlevleri](../mfc/commonly-added-member-functions.md)
