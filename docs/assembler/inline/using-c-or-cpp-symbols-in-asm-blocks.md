---
description: 'Hakkında daha fazla bilgi edinin: __asm bloklarında C veya C++ sembolleri kullanma'
title: __asm Bloklarında C veya C++ Simgelerini Kullanma
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
ms.openlocfilehash: 3a2e46ab13bb316cb4761103d34da6c129c97995
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121894"
---
# <a name="using-c-or-c-symbols-in-__asm-blocks"></a>__asm Bloklarında C veya C++ Simgelerini Kullanma

**Microsoft'a Özgü**

Bir **`__asm`** blok, bloğun göründüğü kapsamdaki herhangi bir C veya C++ simgesine başvurabilir. (C ve C++ sembolleri değişken adları, işlev adları ve Etiketler; diğer bir deyişle, sembolik sabitler veya Üyeler olmayan isimlerdir **`enum`** . C++ üye işlevlerini çağrılamaz.)

C ve C++ sembolleri kullanımı için birkaç kısıtlama geçerlidir:

- Her bütünleştirilmiş kod dili ifadesinde yalnızca bir C veya C++ simgesi bulunabilir. Aynı derleme yönergesinde yalnızca **length**, **Type** ve **sıze** ifadeleriyle birden çok sembol görünebilir.

- Bir blokta başvurulan işlevler **`__asm`** , programda daha önce bildirilmelidir (prototipi oluşturulmuş) olmalıdır. Aksi takdirde, derleyici blok içindeki işlev adlarını ve etiketleri ayırt edemez **`__asm`** .

- Bir **`__asm`** blok, MASM ile ayrılmış sözcüklerle aynı yazımla (büyük/küçük harfe bakılmaksızın) C veya C++ sembolleri kullanamaz. MASN ayrılmış sözcükler, **gönderme** ve kayıt adları gibi yönerge adlarını içerir.

- Yapı ve birleşim etiketleri bloklar halinde tanınmıyor **`__asm`** .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
