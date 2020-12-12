---
description: 'Hakkında daha fazla bilgi edinin: sık kullanılan tuş denetimi kullanma'
title: Bir Sık Kullanılan Tuş Denetimi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
ms.openlocfilehash: 078cd4b3d4746723d5996959edad20dd44e9abec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202710"
---
# <a name="using-a-hot-key-control"></a>Bir Sık Kullanılan Tuş Denetimi Kullanma

Sık kullanılan anahtar denetiminin tipik kullanımı aşağıdaki kalıbı izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmişse, iletişim kutusu oluşturulduğunda oluşturma otomatik olur. (Sık kullanılan anahtar denetimine karşılık gelen iletişim sınıfınızın bir [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) üyesine sahip olmanız gerekir.) Alternatif olarak, denetimi herhangi bir pencerenin alt penceresi olarak oluşturmak için üye [Oluştur](../mfc/reference/chotkeyctrl-class.md#create) işlevini de kullanabilirsiniz.

- Denetim için varsayılan bir değer ayarlamak istiyorsanız, [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) üye işlevini çağırın. Belirli kaydırma durumlarını yasaklamak istiyorsanız, [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules)' ı çağırın. İletişim kutusundaki denetimler için, bunu yapmak için iyi bir zaman, iletişim kutusunun [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işleviydi.

- Kullanıcı, sık kullanılan tuş denetimi odağa sahip olduğunda, kısayol tuşuna basarak Denetim ile etkileşime girer. Kullanıcı daha sonra bu görevin tamamlandığını, belki de iletişim kutusunda bir düğmeye tıklayarak belirtir.

- Programınızın kullanıcının bir etkin anahtar seçtiği bildirildiğinde, etkin anahtar denetiminden sanal anahtar ve kaydırma durumu değerlerini almak için [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) üye işlevini kullanması gerekir.

- Kullanıcının hangi anahtara seçili olduğunu öğrendikten sonra, etkin anahtar [ayarlama](../mfc/setting-a-hot-key.md)bölümünde açıklanan yöntemlerden birini kullanarak etkin anahtarı ayarlayabilirsiniz.

- Sık kullanılan tuş denetimi bir iletişim kutusunda ise, ve `CHotKeyCtrl` nesnesi otomatik olarak yok edilir. Aksi takdirde, hem denetimin hem de `CHotKeyCtrl` nesnenin düzgün şekilde yok edildiğini güvence altına almanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
