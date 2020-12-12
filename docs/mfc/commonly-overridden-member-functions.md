---
description: 'Daha fazla bilgi edinin: genellikle geçersiz kılınan üye Işlevleri'
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
ms.openlocfilehash: 54fb55716a0e0ac7db0e81ec81ed1b9732f07243
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310583"
---
# <a name="commonly-overridden-member-functions"></a>Yaygın Olarak Geçersiz Kılınan Üye İşlevleri

Aşağıdaki tabloda, türetilmiş sınıfınıza geçersiz kılmak için en olası üye işlevleri listelenmektedir `CDialog` .

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>CDialog sınıfının genellikle geçersiz kılınan üye Işlevleri

|Üye işlevi|Yanıt verdiği ileti|Geçersiz kılmanın amacı|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|İletişim kutusu denetimlerini başlatın.|
|`OnOK`|Düğme **IDOK** için **BN_CLICKED**|Kullanıcı Tamam düğmesine tıkladığında yanıt verir.|
|`OnCancel`|Düğme **IDCANCEL** için **BN_CLICKED**|Kullanıcı Iptal düğmesine tıkladığında yanıt verir.|

`OnInitDialog`, `OnOK` ve `OnCancel` sanal işlevlerdir. Bunları geçersiz kılmak için, [MFC sınıf Sihirbazı 'nı](reference/mfc-class-wizard.md)kullanarak türetilmiş iletişim sınıfınızda bir geçersiz kılma işlevi bildirirsiniz.

`OnInitDialog` iletişim kutusu görüntülenmeden hemen önce çağrılır. Varsayılan `OnInitDialog` işleyiciyi, genellikle işleyicisindeki ilk eylem olarak, geçersiz kılmanızda çağırmanız gerekir. Varsayılan olarak, `OnInitDialog` odağın iletişim kutusunda ilk denetime ayarlanması gerektiğini belirtmek Için **true** değerini döndürür.

`OnOK` genellikle modsuz ancak kalıcı olmayan iletişim kutuları için geçersiz kılınır. Kalıcı bir iletişim kutusu için bu işleyiciyi geçersiz kılarsınız, çağrıldığından emin olmak için, geçersiz kılmanızda temel sınıf sürümünü çağırın — `EndDialog` veya `EndDialog` kendi kendinize çağrı yapın.

`OnCancel` genellikle kalıcı olmayan iletişim kutuları için geçersiz kılınır.

Bu üye işlevleri hakkında daha fazla bilgi için bkz. *MFC başvurusu* Içindeki sınıf [CDialog](reference/cdialog-class.md) ve [MFC 'deki iletişim kutularıyla çalışma](life-cycle-of-a-dialog-box.md)hakkında tartışma.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](dialog-boxes.md)<br/>
[Yaygın olarak eklenen üye Işlevleri](commonly-added-member-functions.md)
