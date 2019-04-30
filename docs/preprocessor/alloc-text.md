---
title: alloc_text
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
ms.openlocfilehash: 399e8956a511f289b480e66db7f03cac0a6c7c20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389365"
---
# <a name="alloctext"></a>alloc_text
Belirtilen işlev tanımlarının bulunduğu kod bölümünü adlandırır. Pragma, işlev bildirimcisi ve adlandırılan işlevlerin işlev tanımı arasında gerçekleşmelidir.

## <a name="syntax"></a>Sözdizimi

```
#pragma alloc_text( "
textsection
", function1, ... )
```

## <a name="remarks"></a>Açıklamalar

**Alloc_text** pragma işlemez C++ üye işlevlerini veya aşırı yüklenmiş işlevler. Yalnızca C bağlantısıyla bildirilen işlevler için geçerlidir; diğer bir deyişle, bildirilen işlevler **extern "C"** bağlama belirtimi. Bu pragmayı C++ bağlantısı olan bir işlevde kullanırsanız, bir derleyici hatası oluşturulur.

İşlev adresi kullanarak bu yana `__based` , bölüm konumları kullanılmasını gerektiren belirtilmesi desteklenmiyor **alloc_text** pragması. Tarafından belirtilen adı *textsection* çift tırnak içine alınmalıdır.

**Alloc_text** pragması, sonra bildirimlerini herhangi belirli işlevlerin ve bu işlevlerin tanımlarından önce görünmelidir.

Başvurulan işlevler bir **alloc_text** pragması, pragmayla aynı modülde tanımlanmalıdır. Bu yapılmazsa ve daha sonra farklı bir metin bölümüne tanımlanmamış bir işlev derlenirse, hatanın yakalanması kesin olmaz. Program genellikle düzgün bir şekilde çalışacak olsa da, işlev hedeflenen bölümlerde ayrılmayacaktır.

Diğer sınırlamalar **alloc_text** aşağıdaki gibidir:

- Bir işlev içinde kullanılamaz.

- İşlev bildirildikten sonra, ancak işlev tanımlanmadan önce kullanılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)