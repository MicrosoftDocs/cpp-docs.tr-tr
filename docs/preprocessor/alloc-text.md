---
description: 'Daha fazla bilgi edinin: alloc_text pragma'
title: alloc_text pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
ms.openlocfilehash: 496a083c251684ebba004eef00bf466e72211ada
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301067"
---
# <a name="alloc_text-pragma"></a>alloc_text pragması

Belirtilen işlev tanımlarının bulunduğu kod bölümünü adlandırır. Pragma, işlev bildirimcisi ve adlandırılan işlevlerin işlev tanımı arasında gerçekleşmelidir.

## <a name="syntax"></a>Syntax

> **#pragma alloc_text (** "*textsection*" **,** *işlev1* [**,** *function2* ...] **)**

## <a name="remarks"></a>Açıklamalar

**Alloc_text** pragma, C++ üye işlevlerini veya aşırı yüklenmiş işlevleri işlemez. Yalnızca C bağlantısıyla belirtilen işlevler için geçerlidir — diğer bir deyişle, **extern "C"** bağlantı belirtimiyle belirtilen işlevler. Bu pragmayı C++ bağlantısı olan bir işlevde kullanırsanız, bir derleyici hatası oluşturulur.

Kullanılarak işlev adresleme **`__based`** desteklenmediğinden, Bölüm konumlarının belirtilmesi **alloc_text** pragma 'un kullanılmasını gerektirir. *Textsection* tarafından belirtilen ad çift tırnak işareti içine alınmalıdır.

**Alloc_text** pragma, belirtilen işlevlerin ve bu işlevlerin tanımlarından önce bildirimlerinden sonra gelmelidir.

Bir **alloc_text** pragma içinde başvurulan işlevler pragma ile aynı modülde tanımlanmalıdır. Aksi takdirde, tanımsız bir işlev daha sonra farklı bir metin bölümüne derlenirse, hata yakalanmayabilir veya yakalanmayabilir. Program genellikle düzgün bir şekilde çalışacak olsa da, işlev hedeflenen bölümlerde ayrılmayacaktır.

**Alloc_text** diğer sınırlamalar aşağıdaki gibidir:

- Bir işlev içinde kullanılamaz.

- İşlev bildirildikten sonra, ancak işlev tanımlanmadan önce kullanılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
