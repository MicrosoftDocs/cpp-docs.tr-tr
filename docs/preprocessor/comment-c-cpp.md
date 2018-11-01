---
title: comment (C/C++)
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.comment
- comment_CPP
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
ms.openlocfilehash: ec80e8cf177becdc25bdf49d6dfa9ad9c7794b88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612832"
---
# <a name="comment-cc"></a>comment (C/C++)

Bir yorum kaydı, bir nesne dosyası veya yürütülebilir dosyanın yerleştirir.

## <a name="syntax"></a>Sözdizimi

```
#pragma comment( comment-type [,"commentstring"] )
```

## <a name="remarks"></a>Açıklamalar

*Açıklama türü* , aşağıda açıklanan önceden tanımlanmış tanımlayıcıları, yorum kayıt türünü belirten biridir. İsteğe bağlı *commentstring* olan bazı açıklama türleri için ek bilgi sağlayan bir dize sabit değeri. Çünkü *commentstring* bir değişmez dize sabit değerleri kaçış karakterleri, katıştırılmış tırnak işaretleri ile ilgili tüm kuralları ilişkiden bir dizedir (`"`) ve birleştirme.

### <a name="compiler"></a>derleyicisi

Derleyicinin adını ve sürüm numarası, nesne dosyasına yerleştirir. Bu açıklama kayıt bağlayıcı tarafından göz ardı edilir. Sağlarsanız, bir *commentstring* parametresi için bu bir kayıt türü, derleyici bir uyarı oluşturur.

### <a name="exestr"></a>exestr

Basamak *commentstring* nesne dosyasında. Bağlantı zamanında Bu dize, yürütülebilir dosyada yer alır. Yürütülebilir dosya yüklendiğinde dize belleğe yüklü değil; Ancak, bir programla yazdırılabilir dizeleri dosyalarında bulur bulunabilir. Bir sürüm numarası veya benzer bilgileri yürütülebilir bir dosyaya eklemek üzere bu açıklama kayıt türü bir kullanım içindir.

`exestr` kullanım dışıdır ve gelecek sürümde; kaldırılacak Bağlayıcı yorum kaydı işlemez.

### <a name="lib"></a>lib

Bir kitaplık arama kaydı nesnesi dosyasına yerleştirir. Bu açıklama türü tarafından bulunmalıdır bir *commentstring* adı (ve muhtemelen yol), bağlayıcı arama yapmak istediğiniz kitaplığının içeren parametre. Nesne dosyası Kitaplığı arama kayıtları varsayılan kitaplık adını izler; Bağlayıcı kitaplığı ile belirtilmemiş olması koşuluyla yalnızca, komut satırında adlı gibi bu kitaplığın arar [/nodefaultlıb](../build/reference/nodefaultlib-ignore-libraries.md). Aynı kaynak dosyasında birden çok kitaplık arama kayıtları yerleştirebilirsiniz; Her bir kayıt nesne dosyası içinde kaynak dosyada karşılaşılanaa aynı sırada görünür.

Varsayılan kitaplık ve eklenmiş bir kitaplık sırası önemli ise, ile derleme [/Zl](../build/reference/zl-omit-default-library-name.md) anahtar, varsayılan kitaplık adını nesne modülünde yer engeller. İkinci bir açıklama pragması, ardından, eklenmiş kitaplık sonra varsayılan kitaplık adını eklemek için de kullanılabilir. İle bu pragmaları listelenen kitaplıkları nesne modülü kaynak kodda bulunan aynı sırada görünür.

### <a name="linker"></a>bağlayıcı

Basamak bir [bağlayıcı seçeneği](../build/reference/linker-options.md) nesne dosyasında. Bu açıklama türü, komut satırına geçtiğini veya geliştirme ortamında belirtme yerine bir bağlayıcı seçeneği belirlemek için kullanabilirsiniz. Örneğin, belirtebilirsiniz / INCLUDE seçeneği eklenmesi bir sembol, zorlamak için:

```
#pragma comment(linker, "/include:__mySymbol")
```

Yalnızca aşağıdaki (*açıklama türü*) bağlayıcı tanımlayıcısına geçirilecek bağlayıcı seçenekleri kullanılabilir:

- [/ DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)

- [/ DIŞARI AKTARMA](../build/reference/export-exports-a-function.md)

- [/ INCLUDE](../build/reference/include-force-symbol-references.md)

- [/ MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)

- [/ MERGE](../build/reference/merge-combine-sections.md)

- [/ SECTION](../build/reference/section-specify-section-attributes.md)

### <a name="user"></a>kullanıcı

Genel bir yorum, nesne dosyasına yerleştirir. *Commentstring* parametresi yorumun metni içerir. Bu açıklama kayıt bağlayıcı tarafından göz ardı edilir.

Aşağıdaki pragma EMAPI için aranacak bağlayıcı neden olur. Bağlama sırasında LIB Kitaplığı'nı tıklatın. Bağlayıcı ilk geçerli çalışma dizininde, ardından LIB ortam değişkeninde belirtilen yolda arar.

```
#pragma comment( lib, "emapi" )
```

Aşağıdaki pragması, derleyicinin nesne dosyasında derleyicinin adını ve sürüm numarasını neden olur:

```
#pragma comment( compiler )
```

> [!NOTE]
> Yorum süren bir *commentstring* parametresi, kullanabileceğiniz bir makro burada kullandığınız bir dize sabit değeri, herhangi bir yerde koşuluyla bir dize sabit değeri için makro genişler. Ayrıca, dize sabit değerleri ve dize değişmez değerleri için genişletin makroları herhangi bir birleşimini bitiştirebilirsiniz. Örneğin, aşağıdaki deyim, kabul edilebilir:

```
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )
```

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)