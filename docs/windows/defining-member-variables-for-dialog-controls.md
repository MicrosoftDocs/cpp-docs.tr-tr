---
title: (C++) iletişim kutusu denetimleri için üye değişkenleri tanımlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa4d894fb3fc436abab84bfee11199f59bd66f78
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402401"
---
# <a name="defining-member-variables-for-dialog-controls-c"></a>(C++) iletişim kutusu denetimleri için üye değişkenleri tanımlama

Düğmeleri dışında herhangi bir iletişim kutusu denetimi için bir üye değişkeni tanımlamak için aşağıdaki yöntemi kullanabilirsiniz.

> [!NOTE]
> Bu makale, yalnızca bir MFC projesi içinde iletişim kutusu denetimleri için geçerlidir. ATL projeleri kullanması gereken **yeni Windows iletileri ve olay işleyicileri** iletişim kutusu.

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>(Düğme olmayan) iletişim kutusu denetimi için bir üye değişkeni tanımlamak için

1. İçinde [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md), bir denetim seçin.

2. Tuşlarına basarak çalışırken **Ctrl** anahtar, iletişim kutusu denetimini çift tıklayın.

   [Üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md) görünür.

3. İlgili bilgileri yazın **üye değişkeni ekleme** Sihirbazı. Daha fazla bilgi için [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md).

4. Tıklayın **Tamam** dönmek için **iletişim** Düzenleyici.

   > [!TIP]
   > Herhangi bir iletişim kutusu denetiminden mevcut işleyicisine atlamak için denetimi çift tıklatın.

Ayrıca **üye değişkenleri** sekmesinde **MFC Sınıf Sihirbazı** belirli bir sınıf için yeni üye değişkenlerini ekleyin ve önceden tanımlanmış görüntüleyin.

## <a name="requirements"></a>Gereksinimler

MFC

## <a name="see-also"></a>Ayrıca Bkz.

[İletileri İşlevlere Eşleme](../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[MFC Sınıf Sihirbazı](../mfc/reference/mfc-class-wizard.md)<br/>
[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)<br/>
[Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Bir sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)