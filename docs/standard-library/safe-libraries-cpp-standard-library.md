---
title: 'Güvenli kitaplıklar: C++ Standart Kitaplığı'
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
ms.openlocfilehash: 340d300efb442fedb18b738c275bc0a79f874991
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409739"
---
# <a name="safe-libraries-c-standard-library"></a>Güvenli kitaplıklar: C++ Standart Kitaplığı

Visual C++ Standart daha güvenli hale getirmek için kitaplığı dahil olmak üzere C++ ile birlikte sevk kitaplıkları için çeşitli iyileştirmeler yapılmıştır.

Arabellek Taşması veya diğer kod hatası için neden olabileceği C++ Standart Kitaplığı çeşitli yöntemlerin güvensiz belirlenmiştir. Bu yöntemlerin kullanım önerilmez ve bunları değiştirmek için yeni ve daha güvenli yöntemleri oluşturulmuş. Tüm son bu yeni yöntemler `_s`.

Yineleyiciler ve algoritmaları daha güvenli hale getirmek için çeşitli iyileştirmeler de yapılmıştır. Daha fazla bilgi için [Checked Iterators](../standard-library/checked-iterators.md), [Debug Iterator Support](../standard-library/debug-iterator-support.md) ve [_ıterator_debug_level](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, güvenli eşdeğerlerinin yanı sıra, güvensiz olabilecek C++ Standart Kitaplığı yöntemleri listelenmektedir:

|Güvenli olmayan yöntemi|Güvenli eşdeğeri|
|-------------------------------|----------------------|
|[kopyalama](../standard-library/basic-string-class.md#copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#copy_s)|
|[kopyalama](../standard-library/char-traits-struct.md#copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#copy_s)|

Yukarıdaki güvenli olmayan yöntemlerden birini arayın veya yineleyiciler yanlış kullanırsanız, derleyici oluşturacak [Derleyici Uyarısı (Düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Bu uyarıları devre dışı bırakma hakkında daha fazla bilgi için bkz: [_scl_secure_no_warnıngs](../standard-library/scl-secure-no-warnings.md).

## <a name="in-this-section"></a>Bu Bölümde

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)

[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)

[Denetlenmiş Yineleyiciler](../standard-library/checked-iterators.md)

[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
