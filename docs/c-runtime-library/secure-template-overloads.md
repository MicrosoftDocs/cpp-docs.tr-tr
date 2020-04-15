---
title: Güvenli Şablon Aşırı Yüklemeleri
ms.date: 11/04/2016
f1_keywords:
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES
- _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT
helpviewer_keywords:
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES
- _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT
- secure template overloads
ms.assetid: 562741d0-39c0-485e-8529-73d740f29f8f
ms.openlocfilehash: 6dba60b57616a1656b2791958e460f0268eaa7fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361120"
---
# <a name="secure-template-overloads"></a>Güvenli Şablon Aşırı Yüklemeleri

Microsoft, güvenlikle geliştirilmiş sürümler lehine birçok C Runtime kitaplığı (CRT) işlevlerini devre dışı kılmıştır. Örneğin, `strcpy_s` `strcpy`daha güvenli değiştirme. Amortismana alınan işlevler, belleğin üzerine yazabilen işlemleri engellemedikleri için, yaygın güvenlik hataları kaynaklarıdır. Varsayılan olarak, derleyici bu işlevlerden birini kullandığınızda bir amortisman uyarısı üretir. CRT, daha güvenli türevlerine geçişi kolaylaştırmak için bu işlevler için C++ şablonu aşırı yüklemesağlar.

Örneğin, bu kod snippet bir `strcpy` uyarı oluşturur, çünkü amortismana hazırdır:

```cpp
char szBuf[10];
strcpy(szBuf, "test"); // warning: deprecated
```

Amortisman uyarısı, kodunuzu güvenli olmadığını söylemek için vardır. Kodunuzun belleğin üzerine yazadığını doğruladıysanız, birkaç seçeneğiniz vardır. Uyarıyı yoksaymayı seçebilir, uyarıyı `_CRT_SECURE_NO_WARNINGS` bastırmak için CRT üstbilgileri için ekstreeklemelerden önce sembolü tanımlayabilirsiniz veya kodunuzu kullanmak `strcpy_s`üzere güncelleştirebilirsiniz:

```cpp
char szBuf[10];
strcpy_s(szBuf, 10, "test"); // security-enhanced _s function
```

Şablon aşırı yüklemeleri ek seçenekler sağlar. 1 olarak `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` tanımlarsanız, bu, daha güvenli varyantları otomatik olarak arayan standart CRT işlevlerinin şablon aşırı yüklerini sağlar. 1 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` ise, kodunuzda değişiklik yapılmasına gerek yoktur. Arka planda, arama, `strcpy` otomatik olarak sağlanan `strcpy_s` boyut bağımsız değişkeni ile bir çağrıya değiştirilir.

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1

// ...

char szBuf[10];
strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")
```

Makro, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` sayma alan işlevleri etkilemez. `strncpy` Sayım işlevleri için şablon aşırı yüklemelerini etkinleştirmek için 1'e tanımlayın. `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` Ancak, bunu yapmadan önce, kodunuzu arabellek (yaygın bir hata) boyutu değil karakter sayısı geçer emin olun. Ayrıca, güvenli varyant çağrıldığında işlev çağrısından sonra arabelleğe açıkça bir null sonlandırıcı yazan kod gereksizdir. Kesilme davranışına ihtiyacınız varsa, [_TRUNCATE](../c-runtime-library/truncate.md)bakın.

> [!NOTE]
> Makro `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` da `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` 1 olarak tanımlanır gerektirir. `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 1 olarak tanımlanır `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` ve 0 olarak tanımlanırsa, uygulama herhangi bir şablon aşırı yüklemeyapmaz.

1 olarak `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` tanımladığınızda, güvenli türevlerinin şablon aşırı yüklerini ("_s" ile biten adlar) sağlar. Bu durumda, `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` 1 ise, özgün kodda küçük bir değişiklik yapılmalıdır:

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1

// ...

char szBuf[10];
strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")
```

Yalnızca işlevin adının değiştirilmesi gerekir ("_s" eklenerek); şablon aşırı boyutu bağımsız değişkeni sağlayan ilgilenir.

Varsayılan olarak `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` ve 0 (devre dışı) olarak tanımlanır ve `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` 1 (etkin) olarak tanımlanır.

Bu şablonun aşırı yüklenmesinin yalnızca statik diziler için çalıştığını unutmayın. Dinamik olarak ayrılan arabellekler ek kaynak kodu değişiklikleri gerektirir. Yukarıdaki örnekleri yeniden ziyaret edin:

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1

// ...

char *szBuf = (char*)malloc(10);
strcpy(szBuf, "test"); // still deprecated; you have to change it to
                       // strcpy_s(szBuf, 10, "test");
```

Ve bu:

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1

// ...

char *szBuf = (char*)malloc(10);
strcpy_s(szBuf, "test"); // doesn't compile; you have to change it to
                         // strcpy_s(szBuf, 10, "test");
```

## <a name="see-also"></a>Ayrıca bkz.

[CRT'deki Güvenlik Özellikleri](../c-runtime-library/security-features-in-the-crt.md)<br/>
[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
