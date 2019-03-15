---
title: /homeparams (Kayıt Parametrelerini Yığına Kopyala)
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: a1f9269c7deae6c9ae2e4f198006ad09dd37abc3
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820669"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (Kayıt Parametrelerini Yığına Kopyala)

Kayıtları da işlev girişi ile birlikte kendi konumlarına yazılmasını zorlar parametre geçirildi.

## <a name="syntax"></a>Sözdizimi

> **/ homeparams**

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneği, yalnızca x64 hedefleyen çapraz derleyiciler ve yerel kullanılabilir.

Çağırma kuralı x64 yığın alanı kayıtlara geçirilen parametrelerin bile tüm parametreler için ayrılmasını gerektirir. Daha fazla bilgi için [parametre geçirerek](../../build/x64-calling-convention.md#parameter-passing). Varsayılan olarak, kayıt parametresi, sürüm yapılarında onlar için ayrılan yığın alanı içine kopyalanmaz. Bu programın bir en iyi duruma getirilmiş yayın derlemesinde hata ayıklama zorlaştırır.

Yayın derlemeleri için kullanabileceğiniz **/homeparams** kopyalama zorlamak için seçeneği parametrelerini uygulamanızın hatalarını emin olmak için yığına kaydedin. **/ homeparams** kayıt parametrelerini yığına yüklemek için ek bir döngüyle gerektiğinden bir performans olumsuz anlamına gelmez.

Hata ayıklama yapılarında, her zaman kayıtlara geçirilen parametreleri yığına doldurulur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Derleyici seçeneğini girin **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
