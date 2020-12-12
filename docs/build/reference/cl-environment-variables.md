---
description: 'Daha fazla bilgi edinin: CL ortam değişkenleri'
title: CL ortam değişkenleri
ms.date: 06/06/2019
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 1be95d2c2eddd204846fbcdc8675f28d71c25c0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179180"
---
# <a name="cl-environment-variables"></a>CL ortam değişkenleri

CL aracı aşağıdaki ortam değişkenlerini kullanır:

- \_Tanımlanmışsa, CL ve CL_. CL Aracı, CL ortam değişkeninde tanımlanan seçenekleri ve bağımsız değişkenleri komut satırı bağımsız değişkenlerine ekler ve \_ işlemeden önce CL_ ' de tanımlanan seçenekleri ve bağımsız değişkenleri ekler.

- INCLUDE, Visual Studio yüklemenizin \ınclude alt dizinine işaret etmelidir.

- LIBPATH, [#using](../../preprocessor/hash-using-directive-cpp.md)başvurulan meta veri dosyaları için arama yapılacak dizinleri belirtir. LıBPATH hakkında daha fazla bilgi için bkz. [#using](../../preprocessor/hash-using-directive-cpp.md).

CL veya \_ CL_ ortam değişkenini aşağıdaki sözdizimini kullanarak ayarlayabilirsiniz:

> SET CL = [[*seçenek*]... [*Dosya*]...] [/link *bağlantısı-opt* ...] \
> SET \_ CL \_ = [[*seçenek*]... [*Dosya*]...] [/link *bağlantısı-opt* ...]

CL ve CL_ ortam değişkenlerine yönelik bağımsız değişkenlerle ilgili ayrıntılar için \_ , bkz. [MSVC derleyicisi Command-Line sözdizimi](compiler-command-line-syntax.md).

En sık kullandığınız dosya ve seçenekleri tanımlamak için bu ortam değişkenlerini kullanabilirsiniz. Daha sonra belirli amaçlarla CL için daha fazla dosya ve seçenek sağlamak üzere komut satırını kullanın. CL ve \_ CL_ ortam değişkenleri 1024 karakterle sınırlıdır (komut satırı giriş sınırı).

Eşittir işareti () kullanan bir sembol tanımlamak için [/d](d-preprocessor-definitions.md) seçeneğini kullanamazsınız **=** . Bunun yerine, eşittir işareti için sayı işaretini ( **#** ) kullanabilirsiniz. Bu şekilde, \_ (örneğin, tanımlamak için) açık değerlerle Önişlemci sabitleri tanımlamak üzere CL veya CL_ ortam değişkenlerini kullanabilirsiniz `/DDEBUG#1` `DEBUG=1` .

İlgili bilgiler için bkz. [ortam değişkenlerini ayarlama](../setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Örnekler

Aşağıdaki komut, CL ortam değişkenini ayarlamaya yönelik bir örnektir:

> SET CL =/ZP2/Ox/I\INCLUDE\MYINCLS \LIB\BINMODE. NESNESI

CL ortam değişkeni ayarlandığında, `CL INPUT.C` komut satırına girerseniz, etkin komut şu şekilde olur:

> CL/ZP2/Ox/I\ıNCLUDE\MYINCLS \LIB\BINMODE. OBJ GIRIŞI. ,

Aşağıdaki örnek, düz bir CL komutunun FıLE1. c ve DOSYA2. c kaynak dosyalarını derlemesine ve sonra FıLE1. obj, DOSYA2. obj ve FILE3. obj nesne dosyalarını bağlantılandırmasına neden olur:

> CL = FıLE1 AYARLAYıN. C DOSYA2. ,
> SET \_ CL_ = FILE3. Nesnesi
> CL

Bu ortam değişkenleri, CL çağrısının aşağıdaki komut satırıyla aynı etkiye sahip olmasını sağlar:

> CL FıLE1. C DOSYA2. C FILE3. NESNESI

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici seçeneklerini ayarlama](compiler-command-line-syntax.md) \
[MSVC derleyici seçenekleri](compiler-options.md)
