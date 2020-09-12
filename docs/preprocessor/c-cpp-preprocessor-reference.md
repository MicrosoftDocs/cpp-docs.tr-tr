---
title: C/C++ ön işlemci başvurusu
description: Visual Studio 'da Microsoft C/C++ derleyicisi Önişlemci için başvuru.
ms.date: 09/10/2020
helpviewer_keywords:
- preprocessor
- preprocessor, reference overview
ms.assetid: e4a52843-7016-4f6d-8b40-cb1ace18f805
ms.openlocfilehash: e53f7270a71e5e7c3f456be7d55d49eaf352aecb
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040749"
---
# <a name="cc-preprocessor-reference"></a>C/C++ ön işlemci başvurusu

*C/C++ Önişlemci Başvurusu* , Microsoft c/c++ ' da uygulandığı için Önişlemci 'yi açıklar. Önişlemci, derleyiciye geçirilmeden önce C ve C++ dosyalarında ön işlemleri gerçekleştirir. Kodu koşullu olarak derlemek, dosya eklemek, derleme zamanı hata iletileri belirtmek ve kod bölümlerine makineye özel kurallar uygulamak için Önişlemci 'yi kullanabilirsiniz.

Visual Studio 2019 ' de [/deneysel: Önişlemci](../build/reference/experimental-preprocessor.md) derleyici seçeneği, Önişlemci 'nin yeni bir uygulamasını sunar. Yeni uygulama hala devam etmektedir ve bu nedenle deneysel olarak kabul edilir. Bu, sonunda C99, C11 ve C++ 20 ile uyumlu hale hazırlanmalıdır. Daha fazla bilgi için bkz. [MSVC New Önişlemci Overview](preprocessor-experimental-overview.md).

## <a name="in-this-section"></a>Bu bölümde

[İşlemcisi](preprocessor.md)\
Geleneksel ve yeni uyumlu ön işlemcilere genel bir bakış sağlar.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)\
Genellikle kaynak programların farklı yürütme ortamlarında kolayca değiştirilmesini ve kolayca derlenmesi için kullanılan yönergeleri açıklar.

[Önişlemci işleçleri](../preprocessor/preprocessor-operators.md)\
Yönergesi bağlamında kullanılan, Önişlemciye özgü dört işleci açıklar `#define` .

[Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)\
C ve C++ standartları ve Microsoft C++ tarafından belirtilen şekilde önceden tanımlanmış makroları açıklar.

[Pragmaları](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
Her derleyicinin, C ve C++ dilleri ile genel uyumluluğu korurken makine ve işletim sistemine özgü özellikler sunmasına olanak tanıyan pragmalar açıklanmaktadır.

## <a name="related-sections"></a>İlgili bölümler

[C++ dil başvurusu](../cpp/cpp-language-reference.md)\
C++ dilinin Microsoft uygulamasına yönelik başvuru malzemeleri sağlar.

[C dil başvurusu](../c-language/c-language-reference.md)\
C dilinin Microsoft uygulamasına yönelik başvuru malzemeleri sağlar.

[C/C++ derleme başvurusu](../build/reference/c-cpp-building-reference.md)\
Derleyici ve bağlayıcı seçeneklerini tartışan konuların bağlantılarını sağlar.

[Visual Studio projeleri-C++](../build/creating-and-managing-visual-cpp-projects.md)\
Visual Studio 'da, proje sisteminin C++ projeniz için dosyaları bulmak üzere arayacağını belirtmenize olanak tanıyan Kullanıcı arabirimini açıklar.
