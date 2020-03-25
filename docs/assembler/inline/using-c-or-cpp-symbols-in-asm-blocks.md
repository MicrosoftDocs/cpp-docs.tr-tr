---
title: __asm Bloklarında C veya C++ Simgelerini Kullanma
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
ms.openlocfilehash: fd9f8b444d263818aca1b16260f70730d5350e7c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169116"
---
# <a name="using-c-or-c-symbols-in-__asm-blocks"></a>__asm Bloklarında C veya C++ Simgelerini Kullanma

**Microsoft 'a özgü**

`__asm` bloğu, bloğun göründüğü kapsamdaki herhangi bir C C++ veya simgeye başvurabilir. (C ve C++ semboller değişken adlarıdır, işlev adları ve Etiketler; diğer bir deyişle, sembolik sabitler veya `enum` üyeleri olmayan isimlerdir. Üye işlevleri çağrılamaz C++ .)

C ve C++ sembollerin kullanımı için birkaç kısıtlama geçerlidir:

- Her bütünleştirilmiş kod dili ifadesinde yalnızca bir C veya C++ sembol bulunabilir. Aynı derleme yönergesinde yalnızca **length**, **Type**ve **sıze** ifadeleriyle birden çok sembol görünebilir.

- `__asm` bloğunda başvurulan işlevler, programda daha önce bildirilmelidir (prototipi oluşturulmuş). Aksi halde, derleyici `__asm` bloğundaki işlev adlarını ve etiketleri ayırt edemez.

- `__asm` bloğu, MASM ile ayrılmış sözcüklerle C++ (büyük/küçük harfe bakılmaksızın) aynı yazımla sahip herhangi bir C veya sembol kullanamaz. MASN ayrılmış sözcükler, **gönderme** ve kayıt adları gibi yönerge adlarını içerir.

- Yapı ve birleşim etiketleri `__asm` bloklara göre tanınmıyor.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
