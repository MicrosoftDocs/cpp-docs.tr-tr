---
title: Bir kısayol tuşu denetimini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be0d27016204724672c23f04fdee38f01b69e6a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372296"
---
# <a name="using-a-hot-key-control"></a>Bir Sık Kullanılan Tuş Denetimi Kullanma

Tipik bir kısayol tuşu denetimini kullanımını aşağıdaki deseni izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmezse, iletişim kutusu oluşturulurken oluşturma otomatik olarak gerçekleşir. (Olması bir [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) sık kullanılan tuş denetimi için karşılık gelen iletişim sınıfınızı üye.) Alternatif olarak, [Oluştur](../mfc/reference/chotkeyctrl-class.md#create) herhangi bir pencerenin alt pencere olarak denetimi oluşturmak için üye işlevi.

- Bir denetim için varsayılan değeri ayarlamak istiyorsanız, çağrı [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) üye işlevi. Belirli kaydırma durumları engellemek istiyorsanız, çağrı [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules). Bir iletişim kutusu denetimleri için bunu yapmak için bir iletişim kutusunun zamandır [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.

- Kullanıcı, sık kullanılan tuş denetimi odağa sahip olduğunda, bir kısayol tuş bileşimi tuşlarına basarak denetimle etkileşim kurar. Kullanıcı ardından şekilde iletişim kutusunda bir düğmeye tıklayarak bu görev belki de tam gösterir.

- Programınızı kullanıcının sık kullanılan tuş seçtiği bildirildiğinde, üye işlevi kullanmalıdır [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) sık kullanılan tuş denetimi sanal anahtar ve shift durum değerlerini almak için.

- Seçili kullanıcının ne anahtar öğrendikten sonra açıklanan yöntemlerden birini kullanarak bir kısayol tuşu ayarlayabilirsiniz [sık kullanılan tuş ayarlama](../mfc/setting-a-hot-key.md).

- Sık kullanılan tuş denetimi bir iletişim kutusunda, varsa onu ve `CHotKeyCtrl` nesne otomatik olarak silinecektir. Her iki denetim sağlamak ihtiyacınız değil, varsa ve `CHotKeyCtrl` nesne düzgün bir şekilde yok.

## <a name="see-also"></a>Ayrıca Bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

