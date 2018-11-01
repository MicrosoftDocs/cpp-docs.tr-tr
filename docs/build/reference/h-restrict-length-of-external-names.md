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
ms.openlocfilehash: 194f8d2c87eb6aa307f417ff022e7975edf2ccc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489836"
---
# <a name="h-restrict-length-of-external-names"></a>/H (Dış Adların Uzunluğunu Kısıtla)

Kullanım dışı. Dış adların uzunluğunu kısıtlar.

## <a name="syntax"></a>Sözdizimi

> **/H**<em>numarası</em>

## <a name="arguments"></a>Arguments

*Sayı*<br/>
Dış adlar bir programda izin verilen en büyük uzunluğunu belirtir.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, dış (ortak) adların uzunluğunu 2.047 karakterdir. Bu, C ve C++ programları için geçerlidir. Kullanarak **/H** yalnızca tanımlayıcıları için izin verilen uzunluk sınırını azaltın, artırmak değildir. Arasında boşluk **/H** ve *numarası* isteğe bağlıdır.

Dış adlar daha uzun bir program içeriyorsa *numarası*, ek karakterler yoksayılır. Bir program olmadan derlerseniz **/H** ve tanımlayıcı 2.047'den fazla karakter içeriyorsa, derleyici oluşturacak [önemli hata C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md).

Tüm derleyici tarafından oluşturulan altçizgiyi uzunluğu sınırı içerir (**\_**) veya at işareti (**\@**). Bu karakterler, tanımlayıcı bir parçasıdır ve önemli bir konuma taşıyın.

- Derleyici bir alt çizgi ekler (**\_**) değiştiren adlarına `__cdecl` (varsayılan) ve `__stdcall` işaretini çağırma kuralları ve önde gelen (**\@** ) değiştiren adlarına `__fastcall` çağırma kuralı.

- Adlarını değiştiren derleyici bağımsız değişkeni boyut bilgileri ekler `__fastcall` ve `__stdcall` çağırma kuralları ve C++ adları için tür bilgilerini ekler.

İlginizi çekebilecek **/H** yararlıdır:

- Karma dil veya taşınabilir programlar oluşturduğunuzda.

- Dış tanımlayıcı için bir uzunluk sınırları zorunlu tuttukları araçlarını kullandığınızda.

- Hata ayıklama sembolleri kullanan boşluk miktarını sınırlamak istediğinizde.

Aşağıdaki örnekte gösterildiği nasıl kullanarak **/H** gerçekten tanımlayıcısı uzunlukları çok sınırlı olması durumunda hatalara neden olabilir:

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

Ayrıca kullanırken dikkatli olmanız gerekir **/H** seçeneği önceden tanımlanmış derleyici tanımlayıcı nedeniyle. En fazla tanımlayıcı uzunluğu çok küçükse, önceden tanımlanmış belirli tanımlayıcıları çözümlenmemiş yanı sıra belirli bir kitaplığı işlev çağrıları olacaktır. Örneğin, varsa `printf` işlevi kullanılır ve seçeneği **/H5** derleme zamanında sembolü belirtilen **_prin** başvurmak için oluşturulacak `printf`, ve bu bulunamayacaktır Kitaplıkta.

Kullanım **/H** ile uyumsuz [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).

**/H** Visual Studio 2005 seçeneği kullanım dışı; en fazla uzunluk sınırları yükseltildi ve **/H** artık gerekli değildir. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** içinde [kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Derleyici seçeneğini girin **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
