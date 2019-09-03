---
title: alloc_text pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
ms.openlocfilehash: 7ddb12b39e068dea42f7a47f7fd937424be43725
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216344"
---
# <a name="alloc_text-pragma"></a>alloc_text pragması

Belirtilen işlev tanımlarının bulunduğu kod bölümünü adlandırır. Pragma, işlev bildirimcisi ve adlandırılan işlevlerin işlev tanımı arasında gerçekleşmelidir.

## <a name="syntax"></a>Sözdizimi

> **#pragma alloc_text (** "*textsection*" **,** *işlev1* [ **,** *function2* ...] **)**

## <a name="remarks"></a>Açıklamalar

**Alloc_text** pragma, üye işlevlerini veya C++ aşırı yüklenmiş işlevleri işlemez. Yalnızca C bağlantısıyla belirtilen işlevler için geçerlidir — diğer bir deyişle, **extern "C"** bağlantı belirtimiyle belirtilen işlevler. Bu pragmayı C++ bağlantısı olan bir işlevde kullanırsanız, bir derleyici hatası oluşturulur.

Kullanılarak `__based` işlev adresleme desteklenmediğinden, Bölüm konumlarının belirtilmesi için **alloc_text** pragma kullanılması gerekir. *Textsection* tarafından belirtilen ad çift tırnak işareti içine alınmalıdır.

**Alloc_text** pragma, belirtilen işlevlerin ve bu işlevlerin tanımlarından önce bildirimlerinden sonra gelmelidir.

Bir **alloc_text** pragma içinde başvurulan işlevler pragma ile aynı modülde tanımlanmalıdır. Aksi takdirde, tanımsız bir işlev daha sonra farklı bir metin bölümüne derlenirse, hata yakalanmayabilir veya yakalanmayabilir. Program genellikle düzgün bir şekilde çalışacak olsa da, işlev hedeflenen bölümlerde ayrılmayacaktır.

**Alloc_text** ile ilgili diğer sınırlamalar aşağıdaki gibidir:

- Bir işlev içinde kullanılamaz.

- İşlev bildirildikten sonra, ancak işlev tanımlanmadan önce kullanılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
