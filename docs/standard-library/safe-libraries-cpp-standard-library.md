---
title: 'Güvenli Kitaplıklar: C++ Standart Kitaplığı'
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
ms.openlocfilehash: 782a3610909de01e1a1991dee3a74aee9a131da3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454558"
---
# <a name="safe-libraries-c-standard-library"></a>Güvenli Kitaplıklar: C++ Standart Kitaplığı

Standart Kitaplığı dahil olmak üzere Microsoft C++ile birlikte gelen kitaplıklarda, daha güvenli hale getirmek için çeşitli geliştirmeler yapılmıştır. C++

C++ Standart kitaplıktaki çeşitli yöntemler, bir arabellek taşmasına veya diğer kod hatalarına yol açabileceğinden güvenli olmayabilecek olarak tanımlandı. Bu yöntemlerin kullanımı önerilmez ve bunları değiştirmek için yeni, daha güvenli yöntemler oluşturulmuştur. Tüm bu yeni yöntemler ile biter `_s`.

Yineleyicilerin ve algoritmaların daha güvenli olması için çeşitli geliştirmeler yapılmıştır. Daha fazla bilgi için bkz. [denetlenen yineleyiciler](../standard-library/checked-iterators.md), [hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md) ve [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, güvenli olmayabilecek C++ ve daha güvenli eşdeğer olan standart kitaplık yöntemleri listelenmektedir:

|Güvensiz olabilecek Yöntem|Daha güvenli eşdeğer|
|-------------------------------|----------------------|
|[kopya](../standard-library/basic-string-class.md#copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#copy_s)|
|[kopya](../standard-library/char-traits-struct.md#copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#copy_s)|

Yukarıdaki güvensiz olabilecek yöntemlerden birini çağırırsanız veya yineleyiciler yanlış kullanırsanız, derleyici [Derleyici Uyarısı (düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Bu uyarıları devre dışı bırakma hakkında daha fazla bilgi için, bkz. [_Scl_secure_no_uyarılar](../standard-library/scl-secure-no-warnings.md).

## <a name="in-this-section"></a>Bu Bölümde

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)

[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)

[Denetlenmiş Yineleyiciler](../standard-library/checked-iterators.md)

[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)
