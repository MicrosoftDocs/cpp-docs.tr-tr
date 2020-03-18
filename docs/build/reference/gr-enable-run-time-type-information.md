---
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
ms.openlocfilehash: ee1398b2f9ee78c62fb84aa591e77708cd0d9d83
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439592"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Çalışma Zamanı Türü Bilgileri Etkinleştir)

Çalışma zamanında nesne türlerini denetlemek için kod ekler.

## <a name="syntax"></a>Sözdizimi

```
/GR[-]
```

## <a name="remarks"></a>Açıklamalar

**/Gr** açık olduğunda, derleyici `_CPPRTTI` önişlemci makrosunu tanımlar. Varsayılan olarak, **/gr** açık olur. **/Gr-** çalışma zamanı tür bilgilerini devre dışı bırakır.

Derleyici kodunuzda bir nesne türünü statik olarak çözümleyemezse **/gr** kullanın. Kodunuzun [dynamic_cast işleci](../../cpp/dynamic-cast-operator.md) veya [TypeId](../../cpp/typeid-operator.md)kullanması durumunda genellikle **/gr** seçeneğine ihtiyacınız vardır. Ancak, **/gr** görüntünüzün. rdata bölümlerinin boyutunu artırır. Kodunuz **dynamic_cast** veya **TypeId**kullanmıyorsa, **/gr-** daha küçük bir resim üretebilir.

Çalışma zamanı tür denetimi hakkında daha fazla bilgi için bkz.  *C++ dil başvurusunda* [çalışma zamanı türü bilgileri](../../cpp/run-time-type-information.md) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++**  klasörüne tıklayın.

1. **Dil** Özellik sayfasına tıklayın.

1. **Çalışma zamanı türü bilgilerini etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
