---
title: CL ortam değişkenleri
ms.date: 06/06/2019
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 4d6b1982b1e544459a025d6cb7bee75666e7130e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440252"
---
# <a name="cl-environment-variables"></a>CL ortam değişkenleri

CL aracı aşağıdaki ortam değişkenlerini kullanır:

- Tanımlı ise CL ve \_CL_. CL Aracı, CL ortam değişkeninde tanımlanan seçenekleri ve bağımsız değişkenleri komut satırı bağımsız değişkenlerine ekler ve işlemeden önce \_CL_ tanımlanan seçenekleri ve bağımsız değişkenleri ekler.

- INCLUDE, Visual Studio yüklemenizin \ınclude alt dizinine işaret etmelidir.

- LIBPATH, [#using](../../preprocessor/hash-using-directive-cpp.md)başvurulan meta veri dosyaları için arama yapılacak dizinleri belirtir. LıBPATH hakkında daha fazla bilgi için bkz. [#using](../../preprocessor/hash-using-directive-cpp.md).

Aşağıdaki sözdizimini kullanarak CL veya \_CL_ ortam değişkenini ayarlayabilirsiniz:

> SET CL = [[*seçenek*]... [*Dosya*]...] [/link *bağlantısı-opt* ...] \
> \_CL\_= [[*seçenek*] öğesini ayarlayın... [*Dosya*]...] [/link *bağlantısı-opt* ...]

CL ve \_CL_ ortam değişkenlerine yönelik bağımsız değişkenlerle ilgili ayrıntılar için bkz. [MSVC derleyicisi komut satırı sözdizimi](compiler-command-line-syntax.md).

En sık kullandığınız dosya ve seçenekleri tanımlamak için bu ortam değişkenlerini kullanabilirsiniz. Daha sonra belirli amaçlarla CL için daha fazla dosya ve seçenek sağlamak üzere komut satırını kullanın. CL ve \_CL_ ortam değişkenleri 1024 karakterle sınırlıdır (komut satırı giriş sınırı).

Eşittir işareti ( **=** ) kullanan bir sembol tanımlamak için [/d](d-preprocessor-definitions.md) seçeneğini kullanamazsınız. Bunun yerine, eşittir işareti için sayı işaretini ( **#** ) kullanabilirsiniz. Bu şekilde, (örneğin, `DEBUG=1`tanımlamak için `/DDEBUG#1`) açık değerlerle Önişlemci sabitlerini tanımlamak için CL veya \_CL_ ortam değişkenlerini kullanabilirsiniz.

İlgili bilgiler için bkz. [ortam değişkenlerini ayarlama](../setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Örnekler

Aşağıdaki komut, CL ortam değişkenini ayarlamaya yönelik bir örnektir:

> SET CL =/ZP2/Ox/I\INCLUDE\MYINCLS \LIB\BINMODE. NESNESI

CL ortam değişkeni ayarlandığında, komut satırına `CL INPUT.C` girerseniz, etkin komut şu şekilde olur:

> CL/ZP2/Ox/I\ıNCLUDE\MYINCLS \LIB\BINMODE. OBJ GIRIŞI. ,

Aşağıdaki örnek, düz bir CL komutunun FıLE1. c ve DOSYA2. c kaynak dosyalarını derlemesine ve sonra FıLE1. obj, DOSYA2. obj ve FILE3. obj nesne dosyalarını bağlantılandırmasına neden olur:

> CL = FıLE1 AYARLAYıN. C DOSYA2. ,
> \_CL_ = FILE3 AYARLAYıN. Nesnesi
> CL

Bu ortam değişkenleri, CL çağrısının aşağıdaki komut satırıyla aynı etkiye sahip olmasını sağlar:

> CL FıLE1. C DOSYA2. C FILE3. NESNESI

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici seçeneklerini ayarlama](compiler-command-line-syntax.md) \
[MSVC Derleyicisi Seçenekleri](compiler-options.md)
