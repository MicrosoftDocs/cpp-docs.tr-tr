---
title: açıklama pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.comment
- comment_CPP
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
ms.openlocfilehash: 3175ad5318bcc6fd9aa6233258ccec9033c89be8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219100"
---
# <a name="comment-pragma"></a>açıklama pragması

Bir nesne dosyasına veya yürütülebilir dosyaya bir yorum kaydı koyar.

## <a name="syntax"></a>Sözdizimi

> **#pragma açıklaması (** *Açıklama türü* [ **,** "*Açıklama-dizesi*"] **)**

## <a name="remarks"></a>Açıklamalar

*Açıklama türü* , aşağıda açıklanan, açıklama kaydı türünü belirten önceden tanımlanmış tanımlayıcılardan biridir. İsteğe bağlı *Açıklama dizesi* , bazı açıklama türleri için ek bilgi sağlayan bir dize sabit değeri. *Açıklama dizesi* bir dize sabit değeri olduğundan, dize sabit değerleri için kaçış karakterleri, gömülü tırnak işaretleri (`"`) ve birleştirme ile ilgili tüm kurallara uyar.

### <a name="compiler"></a>derleyicisi

Derleyicinin adını ve sürüm numarasını nesne dosyasına koyar. Bu açıklama kaydı bağlayıcı tarafından yok sayılır. Bu kayıt türü için bir *Açıklama dizesi* parametresi sağlarsanız, derleyici bir uyarı oluşturur.

### <a name="lib"></a>LIB

Nesne dosyasına bir kitaplık arama kaydı koyar. Bu açıklama türü, bağlayıcının aramasını istediğiniz adı (ve muhtemelen yolu) içeren bir *Açıklama dize* parametresi ile birlikte kullanılmalıdır. Kitaplık adı, nesne dosyasındaki varsayılan kitaplık arama kayıtlarını izler; bağlayıcı, kitaplığın [/NODEFAULTLIB](../build/reference/nodefaultlib-ignore-libraries.md)ile belirtilmemesi için komut satırına adlandırılmış gibi, bu kitaplığı arar. Birden çok kitaplık arama kaydını aynı kaynak dosyasına yerleştirebilirsiniz; Her kayıt, nesne dosyasında, kaynak dosyada karşılaşılan sırada görüntülenir.

Varsayılan kitaplık ve eklenen bir kitaplığın sıralaması önemliyse, [/zl](../build/reference/zl-omit-default-library-name.md) anahtarıyla derleme varsayılan kitaplık adının nesne modülüne yerleştirilmesini engeller. İkinci bir açıklama pragma daha sonra, eklenen kitaplıktan sonra varsayılan kitaplığın adını eklemek için kullanılabilir. Bu pragmalarla listelenen kitaplıklar, nesne modülünde, kaynak kodda bulundukları sırada görüntülenir.

### <a name="linker"></a>bağlayıcı

Nesne dosyasına bir [bağlayıcı seçeneği](../build/reference/linker-options.md) koyar. Bu açıklama türünü, komut satırına geçirmek veya geliştirme ortamında belirtmek yerine bir bağlayıcı seçeneği belirtmek için kullanabilirsiniz. Örneğin, bir simgenin eklenmesini zorlamak için/Include seçeneğini belirtebilirsiniz:

```C
#pragma comment(linker, "/include:__mySymbol")
```

Bağlayıcı tanımlayıcısına yalnızca aşağıdaki (*Açıklama türü*) bağlayıcı seçeneklerinin geçirilmesi sağlanır:

- [/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)

- [/EXPORT](../build/reference/export-exports-a-function.md)

- [/INCLUDE](../build/reference/include-force-symbol-references.md)

- [/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)

- [/MERGE](../build/reference/merge-combine-sections.md)

- [/SECTION](../build/reference/section-specify-section-attributes.md)

### <a name="user"></a>kullanıcı

Nesne dosyasına genel bir açıklama koyar. *Comment dize* parametresi açıklama metnini içerir. Bu açıklama kaydı bağlayıcı tarafından yok sayılır.

## <a name="examples"></a>Örnekler

Aşağıdaki pragma, bağlayıcının EMAPı aramasını sağlar. Bağlama sırasında LıB kitaplığı. Bağlayıcı ilk olarak geçerli çalışma dizininde ve sonra LıB ortam değişkeninde belirtilen yolda arama yapar.

```C
#pragma comment( lib, "emapi" )
```

Aşağıdaki pragma, derleyicinin ad ve sürüm numarasını nesne dosyasına yerleştirmesine neden olur:

```C
#pragma comment( compiler )
```

Bir *Comment dize* parametresi alan Yorumlar için, makronun bir dize sabit değerine genişledikçe, bir dize sabit değeri kullandığınız yerde bir makro kullanabilirsiniz. Dize değişmezlerini ve dize değişmez değerlerine genişleterek makroların herhangi bir birleşimini de birleştirebilirsiniz. Örneğin, aşağıdaki ifade kabul edilebilir:

```C
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
