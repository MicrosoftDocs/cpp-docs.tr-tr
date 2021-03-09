---
title: Güvenli Şablon Aşırı Yüklemeleri
description: Gelişmiş güvenlik işlevleri sağlayan Microsoft C çalışma zamanı şablonu aşırı yüklemelerinin açıklaması.
ms.date: 11/04/2016
ms.topic: conceptual
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
ms.openlocfilehash: 69ddeed831bde26de23e0a29ece9f5550de8cf9f
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514531"
---
# <a name="secure-template-overloads"></a>Güvenli Şablon Aşırı Yüklemeleri

Microsoft, güvenliği geliştirilmiş sürümler için çok sayıda C çalışma zamanı kitaplığı (CRT) işlevini kullanımdan kaldırılmıştır. Örneğin, `strcpy_s` için daha güvenli bir değişiklik `strcpy` . Kullanım dışı bırakılan işlevler, belleğin üzerine yazabilecek işlemleri engellemediğinden güvenlik hatalarının yaygın kaynaklarıdır. Varsayılan olarak, derleyici bu işlevlerden birini kullandığınızda kullanımdan kaldırma uyarısı üretir. CRT, daha güvenli çeşitlere geçişi kolaylaştırmaya yardımcı olmak için bu işlevler için C++ şablonu aşırı yüklemeleri sağlar.

Örneğin, bu kod parçacığı kullanım dışı olduğundan bir uyarı oluşturur `strcpy` :

```cpp
char szBuf[10];
strcpy(szBuf, "test"); // warning: deprecated
```

Kullanımdan kaldırma uyarısı, kodunuzun güvenli olmayabileceğini bildiren bir sorun olduğunu bildirir. Kodunuzun belleğin üzerine yazamayacağını doğruladıysanız, birkaç seçeneğiniz vardır. Uyarıyı yok saymayı seçebilirsiniz, daha sonra `_CRT_SECURE_NO_WARNINGS` uyarıyı bastırmak IÇIN CRT üst bilgilerinde Include deyimleriyle önce sembolü tanımlayabilir veya kodunuzu kullanmak üzere güncelleştirebilirsiniz `strcpy_s` :

```cpp
char szBuf[10];
strcpy_s(szBuf, 10, "test"); // security-enhanced _s function
```

Şablon aşırı yüklemeleri ek seçenekler sağlar. `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`1 olarak tanımlarsanız, bu, daha güvenli çeşitleri otomatik olarak çağıran standart CRT işlevlerinin şablon aşırı yüklerini sağlar. `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`1 ise, kodunuzda herhangi bir değişiklik yapmanız gerekmez. Arka planda, ' a yapılan çağrı, `strcpy` `strcpy_s` otomatik olarak sağlanan boyut bağımsız değişkeniyle bir çağrıya dönüştürülür.

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1

// ...

char szBuf[10];
strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")
```

Makro, gibi `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` bir sayı alan işlevleri etkilemez `strncpy` . Sayı işlevleri için şablon aşırı yüklerini etkinleştirmek üzere, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 1 olarak tanımlayın. Ancak bunu yapmadan önce, kodunuzun, arabelleğin boyutunu (yaygın bir hata) değil karakter sayısını geçirdiğinizden emin olun. Ayrıca, güvenli değişken çağrılırsa işlev çağrısının sonuna açıkça bir null Sonlandırıcı yazan kod. Kesme davranışına ihtiyacınız varsa, bkz. [_TRUNCATE](../c-runtime-library/truncate.md).

> [!NOTE]
> Makro için `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` de 1 olarak tanımlanmış olması gerekir. `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT`1 olarak tanımlandıysa ve `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` 0 olarak tanımlanmışsa, uygulama herhangi bir şablon aşırı yüklemesi gerçekleştirmez.

`_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES`1 olarak tanımladığınızda, güvenli çeşitlerin şablon aşırı yüklerini ("_s" ile biten adlar) sağlar. Bu durumda, 1 ise, `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` özgün koda bir küçük değişiklik yapılmalıdır:

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1

// ...

char szBuf[10];
strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")
```

Yalnızca işlevin adının değiştirilmesi gerekir ("_s" eklenerek); şablon aşırı yüklemesi, boyut bağımsız değişkenini sağlamaktan yararlanır.

Varsayılan olarak, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 0 (devre dışı) olarak tanımlanır ve `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` 1 (etkin) olarak tanımlanır.

Bu şablon yalnızca statik diziler için çalışır. Dinamik olarak ayrılmış arabellekler ek kaynak kodu değişiklikleri gerektirir. Yukarıdaki örnekler yeniden ziyaret edilecek:

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1

// ...

char *szBuf = (char*)malloc(10);
strcpy(szBuf, "test"); // still deprecated; change it to
                       // strcpy_s(szBuf, 10, "test");
```

Ve şunları yapın:

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1

// ...

char *szBuf = (char*)malloc(10);
strcpy_s(szBuf, "test"); // doesn't compile; change it to
                         // strcpy_s(szBuf, 10, "test");
```

## <a name="see-also"></a>Ayrıca bkz.

[CRT 'daki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md)<br/>
[C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
