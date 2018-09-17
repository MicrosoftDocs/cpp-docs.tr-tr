---
title: ASSERT yerine VERIFY kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- assert
dev_langs:
- C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea6ea90460f3fd28724ee1fd34dfdeb3f6ae80b2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711782"
---
# <a name="using-verify-instead-of-assert"></a>ASSERT Yerine VERIFY Kullanma

MFC uygulamanızı hata ayıklama sürümünü çalıştırdığınızda, herhangi bir sorun yok varsayalım. Ancak aynı uygulamanın yayın sürümünü çöküyor, hatalı sonuçlar verir ve/veya bazı diğer anormal bir davranış gösteriyor.

Doğru bir şekilde gerçekleştirir doğrulamak için bir onay deyimi önemli kod yerleştirdiğinizde bu soruna neden olabilir. MFC programı bir yayın derlemesinin ASSERT deyimleri satırlarıdır olduğundan, bir yayın yapı içinde kod çalıştırmaz.

Bir işlev çağrısı başarılı olduğunu doğrulamak için onayı kullanıyorsanız, kullanmayı [doğrulama](../../mfc/reference/diagnostic-services.md#verify) yerine. VERIFY makrosu hem hata ayıklama bağımsız kendi değişkenlerini değerlendirir ve uygulamayı yayın oluşturur.

Başka bir tekniktir işlevin dönüş değeri geçici bir değişkene atayın ve ardından değişkeni bir onay deyimi içinde test etmek için tercih edilir.

Aşağıdaki kod parçası inceleyin:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Bu kod, bir MFC uygulaması, bir hata ayıklama sürümünde mükemmel bir şekilde çalışır. Çağrı `calloc( )` başarısız dosya ve satır numarası içeren bir tanılama iletisi görünür. Ancak, bir perakende bir MFC uygulaması oluşturun:

- çağrı `calloc( )` hiçbir zaman oluşur, bırakarak `buf` başlatılmamış, veya

- `strcpy_s( )` kopya "`Hello, World`" bellek, büyük olasılıkla uygulama kilitlenme veya sistem yanıt vermeyi durdurmasına neden rastgele bir parçası olarak veya

- `free()` hiçbir zaman ayrılan belleği boşaltmak çalışır.

ASSERT doğru bir şekilde kullanmak için kodu örneği aşağıdaki değiştirilmelidir:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );
ASSERT( buf != NULL );
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Veya bunun yerine doğrulama kullanabilirsiniz:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>Ayrıca Bkz.

[Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)