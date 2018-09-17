---
title: CL ortam değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74ac2cb1ad28720cc45aec4f6258d1152a55e861
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722741"
---
# <a name="cl-environment-variables"></a>CL Ortam Değişkenleri

CL Aracı'nı aşağıdaki ortam değişkenleri kullanır:

- CL ve \_CL\_, tanımlı değilse. CL araç seçenekleri ve komut satırı bağımsız değişkenleri için CL ortam değişkeninde tanımlanan değişkenleri ekler ve seçenekleri ekler ve bağımsız değişkenler tanımlanan \_CL\_, işlemeden önce.

- , Visual C++ yüklemenizin \include alt dizinine işaret etmelidir içerir.

- İle başvurulan meta veri dosyaları için aranacak dizinleri belirtir, LIBPATH [#using](../../preprocessor/hash-using-directive-cpp.md). Bkz: `#using` LIBPATH hakkında daha fazla bilgi için.

CL ayarlayabilirsiniz veya \_CL\_ aşağıdaki sözdizimini kullanarak ortam değişkeni:

> AYARLAMA CL = [[*seçeneği*]... [*dosya*]...] [/ link *bağlantı iyileştirilmiş* ...] AYARLAMA \_CL\_= [[*seçeneği*]... [*dosya*]...] [/ link *bağlantı iyileştirilmiş* ...]

CL bağımsız değişkenleri hakkında ayrıntılı bilgi için ve \_CL\_ bkz. ortam değişkenleri [derleyici komut satırı sözdizimi](../../build/reference/compiler-command-line-syntax.md).

Dosyaları ve en sık kullandığınız seçenekleri tanımlamak için bu ortam değişkenlerini kullanma ve belirli amaçlarla belirli dosyaları ve seçenekleri tanımlamak için komut satırını kullanın. CL ve \_CL\_ ortam değişkenlerini (komut satırı giriş sınırı) 1024 karakterle sınırlıdır.

/D seçeneği, bir eşittir işareti (=) kullanan simge tanımlamak için kullanamazsınız. Sayı işaretiyle (#) için bir eşittir işareti yerine kullanabilirsiniz. Bu şekilde, CL kullanabilirsiniz veya \_CL\_ açık değerlerle önişlemci sabitleri tanımlamak için ortam değişkenlerini — Örneğin, `/DDEBUG#1` tanımlamak için `DEBUG=1`.

İlgili bilgiler için bkz. [ortam değişkenlerini ayarlamak](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Örnekler

CL ortam değişkenini ayarlayarak bir örnek verilmiştir:

> CL = / Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE ayarlayın. OBJ

Bu ortam değişkeni ayarlandığında, girerseniz `CL INPUT.C` komut satırında, bu etkili bir komuttur:

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE. OBJ GİRİŞ. C

Aşağıdaki örnek, FILE1.c ve FILE2.c kaynak dosyalarını derlemek ve ardından nesne dosyaları FILE1.obj FILE2.obj ve FILE3.obj bağlamak bir düz CL komut neden olur:

> KÜMESİ CL = FILE1'DE. C DOSYA2. C KÜMESİ \_CL\_DOSYA3 =. OBJ TEMİZLE

Bu, aşağıdaki komut satırı ile aynı etkiye sahiptir:

> CL FILE1'DE. C DOSYA2. C DOSYA3. OBJ

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)
