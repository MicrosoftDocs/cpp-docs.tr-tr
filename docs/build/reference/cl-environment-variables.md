---
title: CL ortam değişkenleri
ms.date: 06/06/2019
f1_keywords:
- cl
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 0f7930728ef1bf6bea50c4388d52d30c569a8795
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821527"
---
# <a name="cl-environment-variables"></a>CL ortam değişkenleri

CL Aracı'nı aşağıdaki ortam değişkenleri kullanır:

- CL ve \_tanımlanmışsa CL_. CL araç seçenekleri ve komut satırı bağımsız değişkenleri için CL ortam değişkeninde tanımlanan değişkenleri ekler ve seçenekleri ekler ve bağımsız değişkenler tanımlanan \_CL_, işlemeden önce.

- , Visual Studio yüklemenizin \include alt dizinine işaret etmelidir içerir.

- İle başvurulan meta veri dosyaları için aranacak dizinleri belirtir, LIBPATH [#using](../../preprocessor/hash-using-directive-cpp.md). LIBPATH hakkında daha fazla bilgi için bkz. [#using](../../preprocessor/hash-using-directive-cpp.md).

CL ayarlayabilirsiniz veya \_CL_ ortam değişkeni sözdizimini kullanarak:

> AYARLAMA CL = [[*seçeneği*]... [*dosya*]...] [/ link *bağlantı iyileştirilmiş* ...] \
> AYARLAMA \_CL\_= [[*seçeneği*]... [*dosya*]...] [/ link *bağlantı iyileştirilmiş* ...]

CL bağımsız değişkenleri hakkında ayrıntılı bilgi için ve \_CL_ ortam değişkenlerini bkz [MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md).

Bu ortam değişkenleri, dosyaları ve en sık kullandığınız seçenekleri tanımlamak için kullanabilirsiniz. Ardından, daha fazla dosya ve Seçenekler belirli amaçlar için CL öğesine vermek için komut satırını kullanın. CL ve \_CL_ ortam değişkenlerini (komut satırı giriş sınırı) 1024 karakterle sınırlıdır.

Kullanamazsınız [/D](d-preprocessor-definitions.md) kullanan bir eşittir işareti simge tanımlamak için seçeneği ( **=** ). Bunun yerine, numara işareti kullanabilirsiniz ( **#** ) için eşittir. Bu şekilde, CL kullanabilirsiniz veya \_açık değerlerle önişlemci sabitleri tanımlamak için ortam değişkenlerini CL_ — Örneğin, `/DDEBUG#1` tanımlamak için `DEBUG=1`.

İlgili bilgiler için bkz. [ortam değişkenlerini ayarlamak](../setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Örnekler

Aşağıdaki komut, CL ortam değişkenini ayarlayarak, bir örnek verilmiştir:

> SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ

CL ortam değişkeni ayarlandığında, girerseniz `CL INPUT.C` etkili komut komut satırında olur:

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

Aşağıdaki örnek, FILE1.c ve FILE2.c kaynak dosyalarını derlemek ve ardından nesne dosyaları FILE1.obj FILE2.obj ve FILE3.obj bağlamak bir düz CL komut neden olur:

> KÜMESİ CL = FILE1'DE. C DOSYA2. C \
> SET \_CL_=FILE3.OBJ \
> CL

Bu ortam değişkenlerini şu komut satırı ile aynı etkiye sahip CL çağrısı yapın:

> CL FILE1.C FILE2.C FILE3.OBJ

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici seçeneklerini ayarlama](compiler-command-line-syntax.md) \
[MSVC Derleyicisi Seçenekleri](compiler-options.md)
