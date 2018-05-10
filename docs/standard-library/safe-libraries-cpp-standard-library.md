---
title: 'Güvenli kitaplıklar: C++ Standart Kitaplığı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
dev_langs:
- C++
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a139be1598dfdeaaece5c4b2cf8d253beb754ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="safe-libraries-c-standard-library"></a>Güvenli Kitaplıklar: C++ Standart Kitaplık

Visual C++ Standart daha güvenli hale getirmek için kitaplığı dahil olmak üzere C++ ile gönderilen kitaplıkları bazı geliştirmeler yapılmıştır.

Arabellek Taşması veya diğer kod hatası için neden olabileceği C++ Standart Kitaplığı'nda çeşitli yöntemler güvensiz belirlenmiştir. Bu yöntemlerin kullanılması önerilmez ve bunları değiştirmek için yeni ve daha güvenli yöntemleri oluşturuldu. Tüm son yeni yöntemlerden `_s`.

Bazı geliştirmeler yineleyiciler ve algoritmaları daha güvenli olmasını sağlamak için yapılmıştır. Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md), [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md) ve [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, daha güvenli eşdeğerleriyle yanı sıra, güvenli olmayabilecek C++ Standart Kitaplığı yöntemleri listelenmiştir:

|Olmayabilecek yöntemi|Daha güvenli eşdeğeri|
|-------------------------------|----------------------|
|[Kopyalama](../standard-library/basic-string-class.md#copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#copy_s)|
|[Kopyalama](../standard-library/char-traits-struct.md#copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#copy_s)|

Yukarıdaki olmayabilecek yöntemlerden birini arayın veya yineleyiciler yanlış kullanırsanız, derleyici oluşturacak [Derleyici Uyarısı (Düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Bu uyarıların devre dışı bırakma hakkında daha fazla bilgi için bkz: [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="in-this-section"></a>Bu Bölümde

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)

[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)

[Denetlenmiş Yineleyiciler](../standard-library/checked-iterators.md)

[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
