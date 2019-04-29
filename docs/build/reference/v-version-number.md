---
title: /V (Sürüm Numarası)
ms.date: 11/04/2016
f1_keywords:
- /v
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
ms.openlocfilehash: 7bebd3ab9677bb340203bbf857e4ee9f287e36e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317321"
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

**/V** seçeneği Visual Studio 2005'te; başlayarak kullanım dışı **/V** öncelikle olan sanal cihaz sürücüleri (VXD) oluşturulmasını desteklemede kullanılan ve vxd oluşturma Visual C++ araç takımı tarafından artık desteklenmiyor. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** içinde [kategoriye göre listelenmiş derleyici seçenekleri](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
