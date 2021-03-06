---
description: Daha fazla bilgi edinin:/GR (Run-Time türü bilgilerini etkinleştir)
title: /GR (Çalışma Zamanı Türü Bilgileri Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
ms.openlocfilehash: 61b1a595999e5e00bf6b28c75be2de03467cc4ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200175"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Çalışma Zamanı Türü Bilgileri Etkinleştir)

Çalışma zamanında nesne türlerini denetlemek için kod ekler.

## <a name="syntax"></a>Syntax

```
/GR[-]
```

## <a name="remarks"></a>Açıklamalar

**/Gr** açık olduğunda, derleyici `_CPPRTTI` önişlemci makrosunu tanımlar. Varsayılan olarak, **/gr** açık olur. **/Gr-** çalışma zamanı tür bilgilerini devre dışı bırakır.

Derleyici kodunuzda bir nesne türünü statik olarak çözümleyemezse **/gr** kullanın. Kodunuzun [dynamic_cast işleci](../../cpp/dynamic-cast-operator.md) veya [TypeId](../../cpp/typeid-operator.md)kullanması durumunda genellikle **/gr** seçeneğine ihtiyacınız vardır. Ancak, **/gr** görüntünüzün. rdata bölümlerinin boyutunu artırır. Kodunuz **`dynamic_cast`** veya kullanmıyorsa **`typeid`** , **/gr-** daha küçük bir resim üretebilir.

Çalışma zamanı tür denetimi hakkında daha fazla bilgi için bkz. *C++ dil başvurusunda* [çalışma zamanı türü bilgileri](../../cpp/run-time-type-information.md) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Dil** Özellik sayfasına tıklayın.

1. **Run-Time türü bilgilerini etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
