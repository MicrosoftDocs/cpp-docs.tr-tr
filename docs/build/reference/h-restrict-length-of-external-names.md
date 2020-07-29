---
title: /H (Dış Adların Uzunluğunu Kısıtla)
ms.date: 09/05/2018
f1_keywords:
- /h
helpviewer_keywords:
- public name length
- /H compiler option [C++]
- H compiler option [C++]
- external names
- -H compiler option [C++]
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
ms.openlocfilehash: 9a8976700cfb0f333c2715c573aa2d239e2a8e3a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218994"
---
# <a name="h-restrict-length-of-external-names"></a>/H (Dış Adların Uzunluğunu Kısıtla)

Kullanım dışı. Dış adların uzunluğunu kısıtlar.

## <a name="syntax"></a>Sözdizimi

> **/H**<em>numarası</em>

## <a name="arguments"></a>Arguments

*sayı*<br/>
Bir programda izin verilen en fazla dış ad uzunluğunu belirtir.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, dış (genel) adların uzunluğu 2.047 karakterdir. Bu, C ve C++ programları için geçerlidir. **/H** kullanılması yalnızca izin verilen en fazla tanımlayıcı uzunluğunu azaltabilir, bunu artırmaz. **/H** ve *sayı* arasındaki boşluk isteğe bağlıdır.

Bir program *sayıdan*daha uzun dış adlar içeriyorsa, ek karakterler yok sayılır. Bir programı **/h** olmadan derlerseniz ve bir tanımlayıcı 2.047 'den fazla karakter içeriyorsa, derleyici [Önemli Hata C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md)oluşturacaktır.

Uzunluk sınırı, derleyici tarafından oluşturulan öndeki alt çizgi ( **\_** ) veya işareti ( **\@** ) içerir. Bu karakterler tanımlayıcının bir parçasıdır ve önemli bir konum alır.

- Derleyici, **\_** (varsayılan) ve çağırma kuralları tarafından değiştirilen adlara, baştaki bir alt çizgi () **`__cdecl`** **`__stdcall`** ve **\@** çağrı kuralı tarafından değiştirilen adlara () işareti ekler **`__fastcall`** .

- Derleyici, bağımsız değişken boyut bilgilerini ve çağırma kuralları tarafından değiştirilen adlara ekler **`__fastcall`** **`__stdcall`** ve C++ adlarına tür bilgilerini ekler.

**/H** yararlı bulabilirsiniz:

- Karışık dil veya taşınabilir programlar oluşturduğunuzda.

- Dış tanımlayıcıların uzunluğuna sınır uygulayan araçlar kullandığınızda.

- Bir hata ayıklama derlemesinde simgelerin kullandığı alan miktarını kısıtlamak istediğinizde.

Aşağıdaki örnek, bir tanımlayıcı uzunlukları çok fazla sınırlıysa **/h** 'in nasıl hata verebileceğini gösterir:

```cpp
// compiler_option_H.cpp
// compile with: /H5
// processor: x86
// LNK2005 expected
void func1(void);
void func2(void);

int main() { func1(); }

void func1(void) {}
void func2(void) {}
```

Ayrıca, önceden tanımlanmış derleyici tanımlayıcıları nedeniyle **/h** seçeneğini kullanırken dikkatli olmanız gerekir. En fazla tanımlayıcı uzunluğu çok küçükse, bazı önceden tanımlanmış tanımlayıcıların yanı sıra belirli kitaplık işlev çağrıları da çözülmeyecektir. Örneğin, `printf` işlev kullanılıyorsa ve derleme zamanında **/H5** seçeneği belirtilmişse, sembol **_prin** başvurmak için oluşturulur `printf` ve bu, kitaplıkta bulunamacaktır.

**/H** kullanımı [/GL (tüm program iyileştirmesi)](gl-whole-program-optimization.md)ile uyumsuzdur.

**/H** seçeneği Visual Studio 2005 ' den beri kullanım dışıdır; Maksimum uzunluk sınırları arttı ve **/h** artık gerekli değildir. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, bkz. [kategoriye göre listelenen derleyici seçeneklerinde](compiler-options-listed-by-category.md) **kullanım dışı ve kaldırılmış derleyici seçenekleri** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusunda derleyici seçeneğini girin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
