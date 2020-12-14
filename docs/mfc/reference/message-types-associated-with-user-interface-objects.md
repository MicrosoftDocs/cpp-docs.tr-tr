---
description: 'Hakkında daha fazla bilgi edinin: User-Interface nesneleriyle Ilişkili Ileti türleri'
title: Kullanıcı Arabirimi Nesneleri ile İlişkili İleti Türleri
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.uiobject.msgs
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
ms.openlocfilehash: 78ddb9e5290d17f92714d6b50a57ac097bbf104c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219284"
---
# <a name="message-types-associated-with-user-interface-objects"></a>Kullanıcı Arabirimi Nesneleri ile İlişkili İleti Türleri

Aşağıdaki tabloda, çalıştığınız nesne türleri ve bunlarla ilişkili ileti türleri gösterilmektedir.

### <a name="user-interface-objects-and-associated-messages"></a>Kullanıcı arabirimi nesneleri ve Ilişkili Iletiler

|Nesne Kimliği|İletiler|
|---------------|--------------|
|Sınıf adı, içeren pencereyi temsil eder|Bir [CWnd](../../mfc/reference/cwnd-class.md)-Derived sınıfına uygun Windows iletileri: bir iletişim kutusu, pencere, alt pencere, MDI alt penceresi veya en üstteki çerçeve penceresi.|
|Menü veya hızlandırıcı tanımlayıcı|-KOMUT iletisi (program işlevini yürütür).<br />-UPDATE_COMMAND_UI iletisi (menü öğesini dinamik olarak güncelleştirir).|
|Denetim tanımlayıcısı|Seçili denetim türü için denetim bildirim iletileri.|

## <a name="see-also"></a>Ayrıca bkz.

[Iletileri IŞLEVLERE eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye Işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Sanal Işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Ileti Işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigate-code-cpp.md)
