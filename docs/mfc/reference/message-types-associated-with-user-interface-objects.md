---
title: Kullanıcı arabirimi nesneleri ile ilişkili türleri iletisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.uiobject.msgs
dev_langs:
- C++
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd89f19547eef8ade9d23a6176ea74cb49586857
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860296"
---
# <a name="message-types-associated-with-user-interface-objects"></a>Kullanıcı Arabirimi Nesneleri ile İlişkili İleti Türleri

Aşağıdaki tabloda, birlikte çalıştığınız nesne türlerini ve bunlarla ilişkili ileti türleri gösterilmektedir.

### <a name="user-interface-objects-and-associated-messages"></a>Kullanıcı arabirimi nesneleri ve ilişkili iletileri

|Nesne Kimliği|İletiler|
|---------------|--------------|
|Sınıf adı, kapsayan pencereye temsil eden|Windows iletileri uygun şekilde bir [CWnd](../../mfc/reference/cwnd-class.md)-türetilmiş sınıf: bir iletişim kutusu, penceresi, alt penceresi, MDI alt penceresi veya en üstteki çerçeve penceresi.|
|Menü veya Hızlandırıcı tanımlayıcısı|-KOMUT iletisi (program işlevi çalıştırılır).<br />-UPDATE_COMMAND_UI iletisi (dinamik olarak güncelleştirir. menü öğesi).|
|Denetim Kimliği|Seçili denetim türü için denetimi bildirim iletileri.|

## <a name="see-also"></a>Ayrıca Bkz.

[İletileri İşlevlere Eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Bir sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
