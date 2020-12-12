---
description: 'Hakkında daha fazla bilgi edinin: onaylama yerine VERIFY Kullanma'
title: ASSERT Yerine VERIFY Kullanma
ms.date: 05/06/2019
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
ms.openlocfilehash: cbb878e9184536a6888b84f7861a3e8b7b9ab2b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199057"
---
# <a name="using-verify-instead-of-assert"></a>ASSERT Yerine VERIFY Kullanma

MFC uygulamanızın hata ayıklama sürümünü çalıştırdığınızda bir sorun olmadığını varsayalım. Ancak, aynı uygulamanın yayın sürümü kilitleniyor, hatalı sonuçlar döndürüyor ve/veya bazı olağan dışı davranışlar sergiler.

Bu sorun, önemli kodu doğru şekilde gerçekleştiğini doğrulamak üzere bir onay bildirimine yerleştirdiğinizde meydana gelir. ONAYLAMA deyimleri, bir MFC programının yayın derlemesinde yorum yaptığından, kod bir yayın derlemesi içinde çalışmaz.

Bir işlev çağrısının başarılı olduğunu onaylamak için onay kullanıyorsanız, bunun yerine [VERIFY](../mfc/reference/diagnostic-services.md#verify) kullanmayı deneyin. VERIFY makrosu, uygulamanın hata ayıklama ve yayın Derlemeleriyle kendi bağımsız değişkenlerini değerlendirir.

Başka bir tercih edilen teknik, işlevin dönüş değerini geçici bir değişkene atamak ve sonra değişkeni bir onay ifadesinde test etmek.

Aşağıdaki kod parçasını inceleyin:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Bu kod, bir MFC uygulamasının hata ayıklama sürümünde kusursuz bir şekilde çalışır. Çağrısı `calloc( )` başarısız olursa, dosya ve satır numarasını içeren bir tanılama iletisi görüntülenir. Ancak, bir MFC uygulamasının perakende derlemesinde:

- çağrısı hiçbir şekilde `calloc( )` gerçekleşmez, Başlatılmamış olarak bırakılır `buf` veya

- `strcpy_s( )` " `Hello, World` " öğesini rastgele bir bellek parçasına kopyalar, büyük olasılıkla uygulamayı kilitlenen veya sistemin yanıt vermemesine neden oluyor veya

- `free()` hiç ayrılmamış belleği serbest bırakma girişimleri.

ONAYı doğru bir şekilde kullanmak için, kod örneği aşağıdaki şekilde değiştirilmelidir:

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

Ya da bunun yerine VERIFY kullanabilirsiniz:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>Ayrıca bkz.

[Yayın derleme sorunlarını giderme](fixing-release-build-problems.md)
