---
title: -V (sürüm numarası) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /v
dev_langs:
- C++
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4ad42a72a874537a6307cfc547852f812f4aaaa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707973"
---
# <a name="v-version-number"></a>/V (Sürüm Numarası)

Kullanım dışı. Bir metin dizesi .obj dosyasına katıştırır.

## <a name="syntax"></a>Sözdizimi

```
/Vstring
```

## <a name="arguments"></a>Arguments

*string*<br/>
Sürüm numarası veya telif hakkı bildirimi bir .obj dosyasında katıştırılmış belirten bir dize.

## <a name="remarks"></a>Açıklamalar

Stringcan etiketi bir sürüm numarası veya telif hakkı bildirimi içeren bir .obj dosyası. Dize bir parçası olmaları durumunda herhangi bir boşluk veya sekme karakterlerinden çift tırnak işaretleri (") içine alınması gerekir. Ters eğik çizgi (\\) dizesini bir parçası olmaları durumunda tüm çift tırnak işareti gelmelidir. Arasında boşluk **/V** ve `string` isteğe bağlıdır.

Ayrıca [yorum (C/C++)](../../preprocessor/comment-c-cpp.md) .obj dosyasında derleyicinin adını ve sürüm numarasını yerleştirmek için derleyici açıklama türü bağımsız değişkeni.

**/V** seçeneği Visual Studio 2005'te; başlayarak kullanım dışı **/V** öncelikle olan sanal cihaz sürücüleri (VXD) oluşturulmasını desteklemede kullanılan ve vxd oluşturma Visual C++ araç takımı tarafından artık desteklenmiyor. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** içinde [kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)