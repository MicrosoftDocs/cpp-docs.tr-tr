---
description: 'Daha fazla bilgi edinin: Güvenli Kitaplıklar: C++ standart kitaplığı'
title: 'Güvenli Kitaplıklar: C++ Standart Kitaplık'
ms.date: 11/04/2016
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
ms.openlocfilehash: 7027031054bf9ef7c2a157d6162539bc3801dec4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148895"
---
# <a name="safe-libraries-c-standard-library"></a>Güvenli Kitaplıklar: C++ Standart Kitaplık

C++ standart kitaplığı dahil olmak üzere Microsoft C++ ile birlikte gelen kitaplıklarda, daha güvenli hale getirmek için çeşitli geliştirmeler yapılmıştır.

C++ standart kitaplığı 'ndaki çeşitli yöntemler, bir arabellek taşmasına veya diğer kod hatalarına yol açabileceğinden güvenli olmayabilecek olarak tanımlandı. Bu yöntemlerin kullanımı önerilmez ve bunları değiştirmek için yeni, daha güvenli yöntemler oluşturulmuştur. Tüm bu yeni yöntemler ile biter `_s` .

Yineleyicilerin ve algoritmaların daha güvenli olması için çeşitli geliştirmeler yapılmıştır. Daha fazla bilgi için bkz. [onay yineleyiciler](../standard-library/checked-iterators.md), [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md) ve [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, güvenli olmayabilecek ve daha güvenli eşdeğer olan C++ standart kitaplığı yöntemleri listelenmektedir:

|Güvensiz olabilecek Yöntem|Daha güvenli eşdeğer|
|-------------------------------|----------------------|
|[kopya](../standard-library/basic-string-class.md#copy)|[basic_string:: _Copy_s](../standard-library/basic-string-class.md#copy_s)|
|[kopya](../standard-library/char-traits-struct.md#copy)|[char_traits:: _Copy_s](../standard-library/char-traits-struct.md#copy_s)|

Yukarıdaki güvensiz olabilecek yöntemlerden birini çağırırsanız veya yineleyiciler yanlış kullanırsanız, derleyici [Derleyici Uyarısı (düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Bu uyarıları devre dışı bırakma hakkında daha fazla bilgi için bkz. [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="in-this-section"></a>Bu Bölümde

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)

[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)

[İşaretli yineleyiciler](../standard-library/checked-iterators.md)

[Hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)
