---
description: pragmaMicrosoft C/C++ ' da açıklama yönergesi hakkında daha fazla bilgi edinin
title: açıklamanın pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.comment
- comment_CPP
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragma, comment
- comment pragma
no-loc:
- pragma
ms.openlocfilehash: 8a4df005b672cb108a2b55004a1149693acd4f95
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713070"
---
# <a name="comment-no-locpragma"></a>`comment` pragma

Bir nesne dosyasına veya yürütülebilir dosyaya bir yorum kaydı koyar.

## <a name="syntax"></a>Syntax

> **`#pragma comment(`***Açıklama-türü* [ **`,`** "*Comment-String*"]**`)`**

## <a name="remarks"></a>Açıklamalar

*Açıklama türü* , aşağıda açıklanan, açıklama kaydı türünü belirten önceden tanımlanmış tanımlayıcılardan biridir. İsteğe bağlı *Açıklama dizesi* , bazı açıklama türleri için ek bilgi sağlayan bir dize sabit değeri. *Açıklama dizesi* bir dize sabit değeri olduğundan, kaçış karakterleri, gömülü tırnak işaretleri ( `"` ) ve birleştirme gibi dize sabit değerleri için tüm kurallara uyar.

### <a name="compiler"></a>compiler

Derleyicinin adını ve sürüm numarasını nesne dosyasına koyar. Bu açıklama kaydı bağlayıcı tarafından yok sayılır. Bu kayıt türü için bir *Açıklama dizesi* parametresi sağlarsanız, derleyici bir uyarı oluşturur.

### <a name="lib"></a>LIB

Nesne dosyasına bir kitaplık arama kaydı koyar. Bu açıklama türü, bağlayıcının aramasını istediğiniz ada (ve muhtemelen yol) sahip bir *yorum-dize* parametresi ile birlikte kullanılmalıdır. Kitaplık adı, nesne dosyasındaki varsayılan kitaplık arama kayıtlarını izler. Bağlayıcı, kitaplığı kullanılarak belirtilmediği sürece bu kitaplığı, komut satırında belirtmiş gibi bir şekilde arar [`/nodefaultlib`](../build/reference/nodefaultlib-ignore-libraries.md) . Birden çok kitaplık arama kaydını aynı kaynak dosyasına yerleştirebilirsiniz. Her kayıt, nesne dosyasında kaynak dosyada bulunan sırada görüntülenir.

Varsayılan kitaplık ve eklenen bir kitaplığın sıralaması önemliyse, [`/Zl`](../build/reference/zl-omit-default-library-name.md) anahtarla derleme varsayılan kitaplık adının nesne modülüne yerleştirilmesini engeller. İkinci bir yorum pragma daha sonra, eklenen kitaplıktan sonra varsayılan kitaplığın adını eklemek için kullanılabilir. Bu yönergelerle listelenen kitaplıklar, pragma nesne modülünde, kaynak kodda bulundukları sırada görüntülenir.

### <a name="linker"></a>bağlayıcı

Nesne dosyasına bir [bağlayıcı seçeneği](../build/reference/linker-options.md) koyar. Bu açıklama türünü, komut satırına geçirmek veya geliştirme ortamında belirtmek yerine bir bağlayıcı seçeneği belirtmek için kullanabilirsiniz. Örneğin, bir simgenin eklenmesini zorlamak için/Include seçeneğini belirtebilirsiniz:

```C
#pragma comment(linker, "/include:__mySymbol")
```

Bağlayıcı tanımlayıcısına yalnızca aşağıdaki (*Açıklama türü*) bağlayıcı seçeneklerinin geçirilmesi sağlanır:

- [`/DEFAULTLIB`](../build/reference/defaultlib-specify-default-library.md)

- [`/EXPORT`](../build/reference/export-exports-a-function.md)

- [`/INCLUDE`](../build/reference/include-force-symbol-references.md)

- [`/MANIFESTDEPENDENCY`](../build/reference/manifestdependency-specify-manifest-dependencies.md)

- [`/MERGE`](../build/reference/merge-combine-sections.md)

- [`/SECTION`](../build/reference/section-specify-section-attributes.md)

### <a name="user"></a>kullanıcı

Nesne dosyasına genel bir açıklama koyar. *Comment dize* parametresi açıklama metnini içerir. Bu açıklama kaydı bağlayıcı tarafından yok sayılır.

## <a name="examples"></a>Örnekler

Aşağıdaki, pragma bağlayıcının EMAPI aramasına neden olur. Bağlama sırasında LıB kitaplığı. Bağlayıcı ilk olarak geçerli çalışma dizininde ve sonra LıB ortam değişkeninde belirtilen yolda arama yapar.

```C
#pragma comment( lib, "emapi" )
```

Aşağıda derleyicinin pragma ad ve sürüm numarası nesne dosyasına yerleştirmesine neden olur:

```C
#pragma comment( compiler )
```

Bir *Açıklama dizesi* parametresi alan Yorumlar için, makro bir dize değişmez değerine genişledikçe, bir dize sabit değeri kullandığınız yerde bir makro kullanabilirsiniz. Dize değişmezlerini ve dize değişmez değerlerine genişleterek makroların herhangi bir birleşimini de birleştirebilirsiniz. Örneğin, aşağıdaki ifade kabul edilebilir:

```C
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
