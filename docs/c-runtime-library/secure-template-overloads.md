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
ms.openlocfilehash: dfb13d5a48376efb72a845e2f5e2380407937f5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364538"
---
# <a name="secure-template-overloads"></a>Güvenli Şablon Aşırı Yüklemeleri

Microsoft Gelişmiş Güvenlik sürümleri çok sayıda C çalışma zamanı kitaplığı (CRT) işlevler kullanım dışı. Örneğin, `strcpy_s` için daha güvenli yerini `strcpy`. Kullanım dışı bırakılan işlevler ortak kaynaklardan güvenlik hataların olduğu bellek üzerine yazıp operations engellemez. Bu işlevlerden birini kullandığınızda varsayılan olarak, derleyici kullanımdan kaldırılma uyarısı oluşturur. CRT C++ şablon aşırı yüklemeleri için kolaylaştırmak amacıyla, bu işlevlerin daha güvenli çeşitler geçiş sağlar.

Örneğin, bu kod parçacığı bir uyarı oluşturur çünkü `strcpy` kullanım dışı bırakılmıştır:

```cpp
char szBuf[10];
strcpy(szBuf, "test"); // warning: deprecated
```

Kodunuzu olmayabilecek bildirmek için kullanımdan kaldırılma uyarısı yok. Kodunuzu bellek üzerine yazılamaz doğruladıysanız, birkaç seçeneğiniz vardır. Uyarıyı göz ardı etmeyi seçebilir, simge tanımlayabilir `_CRT_SECURE_NO_WARNINGS` dahil etme deyimlerini CRT için önce uyarıyı veya gizlemek için üstbilgileri kullanmak için kodunuzu güncelleştirebilirsiniz `strcpy_s`:

```cpp
char szBuf[10];
strcpy_s(szBuf, 10, "test"); // security-enhanced _s function
```

Şablon aşırı yüklemeleri ek seçenekler sunar. Tanımlarsanız `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` 1, bu şablon aşırı yüklemeleri daha güvenli çeşitleri otomatik olarak çağıran standart CRT işlevleri sağlar. Varsa `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` kodunuzda hiçbir değişiklik gerekli olan 1 ' dir. Planda, çağrı `strcpy` çağrısı değiştirilecek `strcpy_s` otomatik olarak sağlanan boyut bağımsız değişkeni ile.

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1

// ...

char szBuf[10];
strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")
```

Makro `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` bir sayısı gibi almayan işlevleri etkilemez `strncpy`. Şablon aşırı yüklemeleri sayısı işlevlerine yönelik etkinleştirmek için tanımlama `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 1. Bunu yapmadan önce Bununla birlikte, kodunuzu (sıkça) arabellek boyutunu değil olan karakter sayısı geçtiğinden emin olun. Ayrıca, işlev çağrısı güvenli değişken çağrılırsa gereksizdir sonra kod açıkça bu arabelleğin sonuna bir null Sonlandırıcı yazar. Kesme davranışı gerekirse bkz [_TRUNCATE](../c-runtime-library/truncate.md).

> [!NOTE]
>  Makro `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` gerektiren `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` de 1 tanımlanır. Varsa `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 1 tanımlanır ve `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` tanımlanan 0 uygulama, tüm şablon aşırı yüklemeleri gerçekleştirmez.

Tanımladığınızda `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` isteğe bağlı olarak 1'e ("_Yanları içinde" sonlanan adlara) güvenli çeşitler şablon aşırı yüklemeleri sağlar. Bu durumda, `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` sonra özgün koda küçük bir değişiklik yapılması gerekir, 1 ' dir:

```cpp
#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1

// ...

char szBuf[10];
strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")
```

Yalnızca işlevin adını ("_Yanları" ekleyerek); değiştirilmesi gerekiyor Şablon aşırı yükleme bağımsız değişkenin boyutu sağlama üstlenir.

Varsayılan olarak, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` ve `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 0 (devre dışı) tanımlanır ve `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` 1 (etkin) tanımlanır.

Bu şablon statik diziler için yalnızca iş aşırı unutmayın. Dinamik olarak ayrılan arabellekler ek kaynak kodu değişiklikleri gerektirir. Yukarıdaki örneklerde hakkında yeniden değerlendirme:

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
