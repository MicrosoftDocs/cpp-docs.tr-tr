---
description: Daha fazla bilgi edinin:/V (sürüm numarası)
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
ms.openlocfilehash: 5025642d4ae30315d24754a7ee46268050cfb22a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187058"
---
# <a name="v-version-number"></a>/V (Sürüm Numarası)

Kullanım dışı. . Obj dosyasına bir metin dizesi gömer.

## <a name="syntax"></a>Söz dizimi

```
/Vstring
```

## <a name="arguments"></a>Bağımsız değişkenler

*string*<br/>
Bir. obj dosyasına katıştırılacak sürüm numarasını veya telif hakkı bildirimini belirten bir dize.

## <a name="remarks"></a>Açıklamalar

Stringbir. obj dosyasını bir sürüm numarasıyla veya bir telif hakkı bildirimi ile etiketleyebilir. Dizenin bir parçası olmaları durumunda herhangi bir boşluk veya sekme karakteri çift tırnak işareti (") içine alınmalıdır. Bir ters eğik çizgi ( \\ ), dizenin bir parçası olmaları durumunda tüm çift tırnak işaretlerinden önce gelmelidir. **/V** ile `string` isteğe bağlı bir boşluk.

Derleyicinin adını ve sürüm numarasını. obj dosyasına yerleştirmek için, derleyici açıklama türü bağımsız değişkeniyle birlikte [Comment (C/C++)](../../preprocessor/comment-c-cpp.md) öğesini de kullanabilirsiniz.

**/V** seçeneği Visual Studio 2005 ' den itibaren kullanımdan kaldırılmıştır; **/V** öncelikle sanal cihaz sürücülerini (VXDs) oluşturmayı desteklemek için kullanılır ve VxDs 'in derleme Visual C++ araç takımı tarafından desteklenmez. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, bkz. [kategoriye göre listelenen derleyici seçeneklerinde](compiler-options-listed-by-category.md) **kullanım dışı ve kaldırılmış derleyici seçenekleri** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
