---
title: '/Deneysel: Module (modül desteğini etkinleştir)'
description: 'Modüller için deneysel derleyici desteğini etkinleştirmek için/deneysel: Module derleyici seçeneğini kullanın.'
ms.date: 09/03/2019
f1_keywords:
- module
- /experimental:module
helpviewer_keywords:
- module
- /experimental:module
- Enable module support
ms.openlocfilehash: 82cce127ad5a2f87d11e4a653035bd80ea9f5001
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70294429"
---
# <a name="experimentalmodule-enable-module-support"></a>/Deneysel: Module (modül desteğini etkinleştir)

, Bir taslak C++ 20 standardı tarafından belirtildiği gibi modüller için deneysel derleyici desteğini sunar.

## <a name="syntax"></a>Sözdizimi

> **/deneysel: modül** [ **-** ]

## <a name="remarks"></a>Açıklamalar

/2 [: c + + latest](std-specify-language-standard-version.md) seçeneğiyle birlikte **/deneysel: Module** derleyici seçeneğini kullanarak deneysel modüller desteğini etkinleştirebilirsiniz. Modül desteğini açıkça devre dışı bırakmak için **/deneysel: Module-** kullanabilirsiniz.

Bu seçenek, Visual Studio 2015 güncelleştirme 1 ' den itibaren kullanılabilir. Visual Studio 2019 sürüm 16,2 itibariyle, taslak C++ 20 standart modülleri, Microsoft C++ derleyicisinde tam olarak uygulanmamıştır. Modüller özelliğini kullanarak tek bölümlü modüller oluşturabilir ve Microsoft tarafından sunulan standart kitaplık modüllerini içeri aktarabilirsiniz. Bir modül ve onu tüketen kod aynı derleyici seçenekleriyle derlenmelidir.

Modüller ve bunların nasıl kullanılacağı ve oluşturulacağı hakkında daha fazla bilgi için bkz. [içindeki C++modüllere genel bakış ](../../cpp/modules-cpp.md).

Aşağıda, *ModuleName. IXX*kaynak dosyasından dışarı aktarma modülü oluşturmak için kullanılan derleyici komut satırı seçeneklerine bir örnek verilmiştir:

```cmd
cl /EHsc /MD /experimental:module /module:export /module:name ModuleName /module:wrapper C:\Output\path\ModuleName.h /module:output C:\Output\path\ModuleName.ifc -c ModuleName.ixx
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Yapılandırma açılan **öğesini** **Tüm yapılandırmalara**ayarlayın.

1. **Yapılandırma özellikleri** > **C/C++** dil > Özellik sayfası ' nı seçin.

1. **Modülleri Etkinleştir C++ (deneysel)** özelliğini değiştirin ve sonra **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
