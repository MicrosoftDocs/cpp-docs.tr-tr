---
title: CL Ortam Değişkenleri
ms.date: 05/06/2019
f1_keywords:
- cl
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 620ec386e06b1a0eed91c94e9b2b891d9955fd00
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217627"
---
# <a name="cl-environment-variables"></a>CL Ortam Değişkenleri

CL Aracı'nı aşağıdaki ortam değişkenleri kullanır:

- CL ve \_CL\_, tanımlı değilse. CL araç seçenekleri ve komut satırı bağımsız değişkenleri için CL ortam değişkeninde tanımlanan değişkenleri ekler ve seçenekleri ekler ve bağımsız değişkenler tanımlanan \_CL\_, işlemeden önce.

- , Visual Studio yüklemenizin \include alt dizinine işaret etmelidir içerir.

- İle başvurulan meta veri dosyaları için aranacak dizinleri belirtir, LIBPATH [#using](../../preprocessor/hash-using-directive-cpp.md). Bkz: `#using` LIBPATH hakkında daha fazla bilgi için.

CL ayarlayabilirsiniz veya \_CL\_ aşağıdaki sözdizimini kullanarak ortam değişkeni:

> AYARLAMA CL = [[*seçeneği*]... [*dosya*]...] [/ link *bağlantı iyileştirilmiş* ...] AYARLAMA \_CL\_= [[*seçeneği*]... [*dosya*]...] [/ link *bağlantı iyileştirilmiş* ...]

CL bağımsız değişkenleri hakkında ayrıntılı bilgi için ve \_CL\_ bkz. ortam değişkenleri [MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md).

Dosyaları ve en sık kullandığınız seçenekleri tanımlamak için bu ortam değişkenlerini kullanma ve belirli amaçlarla belirli dosyaları ve seçenekleri tanımlamak için komut satırını kullanın. CL ve \_CL\_ ortam değişkenlerini (komut satırı giriş sınırı) 1024 karakterle sınırlıdır.

/D seçeneği, bir eşittir işareti (=) kullanan simge tanımlamak için kullanamazsınız. Sayı işaretiyle (#) için bir eşittir işareti yerine kullanabilirsiniz. Bu şekilde, CL kullanabilirsiniz veya \_CL\_ açık değerlerle önişlemci sabitleri tanımlamak için ortam değişkenlerini — Örneğin, `/DDEBUG#1` tanımlamak için `DEBUG=1`.

İlgili bilgiler için bkz. [ortam değişkenlerini ayarlamak](../setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Örnekler

CL ortam değişkenini ayarlayarak bir örnek verilmiştir:

> SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ

Bu ortam değişkeni ayarlandığında, girerseniz `CL INPUT.C` komut satırında, bu etkili bir komuttur:

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

Aşağıdaki örnek, FILE1.c ve FILE2.c kaynak dosyalarını derlemek ve ardından nesne dosyaları FILE1.obj FILE2.obj ve FILE3.obj bağlamak bir düz CL komut neden olur:

> SET CL=FILE1.C FILE2.C SET \_CL\_=FILE3.OBJ CL

Bu, aşağıdaki komut satırı ile aynı etkiye sahiptir:

> CL FILE1.C FILE2.C FILE3.OBJ

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçeneklerini Ayarlama](compiler-command-line-syntax.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)
