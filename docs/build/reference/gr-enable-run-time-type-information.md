---
title: /GR (Çalışma Zamanı Türü Bilgileri Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
ms.openlocfilehash: 15ad453b10fd31de97bbc25f8062e628129076f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292126"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Çalışma Zamanı Türü Bilgileri Etkinleştir)

Nesne türlerini çalışma zamanında denetlemek için kod ekler.

## <a name="syntax"></a>Sözdizimi

```
/GR[-]
```

## <a name="remarks"></a>Açıklamalar

Zaman **GR** açıktır, derleyici tanımlar `_CPPRTTI` önişlemci makrosu. Varsayılan olarak, **GR** açıktır. **Denetleyen** çalışma zamanı türü bilgileri devre dışı bırakır.

Kullanım **GR** derleyici, kodunuzda bir nesne türü statik olarak çözümleyememesi durumunda. Genellikle ihtiyacınız **GR** seçeneği kodunuzu kullandığında [dynamic_cast işleci](../../cpp/dynamic-cast-operator.md) veya [TypeID](../../cpp/typeid-operator.md). Ancak, **GR** görüntünüzü .rdata bölümlerini boyutu artar. Kodunuzu kullanmıyorsa **dynamic_cast** veya **TypeID**, **denetleyen** daha küçük bir resmi üretebilir.

Çalışma zamanı tür denetimi hakkında daha fazla bilgi için bkz. [çalışma zamanı türü bilgileri](../../cpp/run-time-type-information.md) içinde *C++ dil başvurusu*.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **dil** özellik sayfası.

1. Değiştirme **çalışma zamanı türü bilgileri etkinleştir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
