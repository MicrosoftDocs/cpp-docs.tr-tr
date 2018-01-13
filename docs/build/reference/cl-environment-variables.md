---
title: "CL ortam değişkenleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba01a980aa24a3ff695479edd08e88d9ea538dcc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cl-environment-variables"></a>CL Ortam Değişkenleri

CL Aracı'nı aşağıdaki ortam değişkenlerini kullanır:

- CL ve \_CL\_, tanımlanmışsa. CL aracı seçenekleri ve komut satırı bağımsız değişkenleri CL ortam değişkenine tanımlanan bağımsız değişkenleri başına ve seçenekleri ekler ve bağımsız değişkenler tanımlanan \_CL\_, işlemeden önce.

- , Visual C++ yüklemenizi \include alt dizinine işaret etmelidir içerir.

- Meta dosyaları ile başvurulan aramak için dizinler belirtir LIBPATH [#using](../../preprocessor/hash-using-directive-cpp.md). Bkz: `#using` LIBPATH hakkında daha fazla bilgi için.

CL ayarlayabilirsiniz veya \_CL\_ aşağıdaki sözdizimini kullanarak ortam değişkeni:

> CL AYARLAMAK = [[*seçeneği*]... [*dosya*]...] [/ link *bağlantı kabul* ...]  
> AYARLAMA \_CL\_= [[*seçeneği*]... [*dosya*]...] [/ link *bağlantı kabul* ...]

CL bağımsız değişkenleri hakkında ayrıntılı bilgi için ve \_CL\_ ortam değişkenleri bkz [derleyici komut satırı sözdizimi](../../build/reference/compiler-command-line-syntax.md).

Bu ortam değişkenleri, en sık kullandığınız seçenekleri ve dosya tanımlamak için kullanın ve belirli dosyaları ve seçenekleri belirli amaçlar için tanımlamak için komut satırını kullanın. CL ve \_CL\_ ortam değişkenlerini (komut satırı giriş sınırı) 1024 karakterle sınırlıdır.

Eşittir işareti (=) kullanan bir simge tanımlamak için /D seçeneği kullanılamaz. Eşittir işareti sayı işareti (#) yerine kullanabilirsiniz. Bu şekilde, CL kullanabilirsiniz veya \_CL\_ açık değerlerle önişlemci sabitleri tanımlamak için ortam değişkenleri — Örneğin, `/DDEBUG#1` tanımlamak için `DEBUG=1`.

İlgili bilgi için bkz: [ortam değişkenlerini ayarlama](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Örnekler

CL ortam değişkeni ayarlamaya ilişkin bir örnek verilmiştir:

> CL = Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE ayarlayın. OBJ

Bu ortam değişkenini ayarlandığında, girerseniz `CL INPUT.C` komut satırında, bu etkili komuttur:

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE. OBJ GİRİŞ. C

Aşağıdaki örnekte kaynak dosyalarını FILE1.c ve FILE2.c derlemek ve ardından nesne dosyaları FILE1.obj, FILE2.obj ve FILE3.obj bağlamak bir düz CL komut neden olur:

> SET CL DOSYA1 =. C DOSYA2. C  
> AYARLAMA \_CL\_DOSYA3 =. OBJ  
> CL  

Aşağıdaki komut satırını aynı etkiye sahiptir:

> CL DOSYA1. C DOSYA2. C DOSYA3. OBJ

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)
