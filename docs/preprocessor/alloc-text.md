---
title: alloc_text | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
dev_langs:
- C++
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d131cee2194ba139fdb99d9c0fa7ae2c922fe84d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073824"
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

**Alloc_text** pragması, C++ üye işlevlerini veya aşırı yüklenmiş işlevleri işlemez. Yalnızca C bağlantısıyla bildirilen işlevler için geçerlidir; diğer bir deyişle, bildirilen işlevler **extern "C"** bağlama belirtimi. Bu pragmayı C++ bağlantısı olan bir işlevde kullanırsanız, bir derleyici hatası oluşturulur.

İşlev adresi kullanarak bu yana `__based` , bölüm konumları kullanılmasını gerektiren belirtilmesi desteklenmiyor **alloc_text** pragması. Tarafından belirtilen adı *textsection* çift tırnak içine alınmalıdır.

**Alloc_text** pragması, sonra bildirimlerini herhangi belirli işlevlerin ve bu işlevlerin tanımlarından önce görünmelidir.

Başvurulan işlevler bir **alloc_text** pragması, pragmayla aynı modülde tanımlanmalıdır. Bu yapılmazsa ve daha sonra farklı bir metin bölümüne tanımlanmamış bir işlev derlenirse, hatanın yakalanması kesin olmaz. Program genellikle düzgün bir şekilde çalışacak olsa da, işlev hedeflenen bölümlerde ayrılmayacaktır.

Diğer sınırlamalar **alloc_text** aşağıdaki gibidir:

- Bir işlev içinde kullanılamaz.

- İşlev bildirildikten sonra, ancak işlev tanımlanmadan önce kullanılmalıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)