---
title: __Declspec(dllimport) kullanarak işlev çağrılarını içeri aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3f7c1bf81b94eebbe32b40053fc5ce3aeaa0bd7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715799"
---
# <a name="importing-function-calls-using-declspecdllimport"></a>__declspec(dllimport) Kullanarak İşlev Çağrılarını İçeri Aktarma

Aşağıdaki kod örneği kullanma işlemini gösterir **_declspec(dllimport)** işlev çağrıları, bir uygulamaya bir DLL'den içeri aktarmak için. Varsayımında `func1` içeren .exe dosyadan ayrı bir DLL içinde yer alan bir işlev, **ana** işlevi.

Olmadan **__declspec(dllimport)**, bu kodu verilir:

```
int main(void)
{
   func1();
}
```

Derleyici, şuna benzeyen bir kod oluşturur:

```
call func1
```

ve şunun gibi çağrıyı bağlayıcı çevirir:

```
call 0x4000000         ; The address of 'func1'.
```

Varsa `func1` adresinin ne olduğunu bilmesinin bir yolu yoktur çünkü başka bir DLL bağlayıcı bunu doğrudan çözümleyemez `func1` olduğu. 16-bit ortamlarında bağlayıcı yükleyici doğru adresi ile çalışma zamanında düzeltme ekini uygulayacağı .exe dosyası bir listede bu kod adresini ekler. 32 bit ve 64-bit ortamlarında hangi adresi bilen bir dönüştürücü bağlayıcı oluşturur. Bir 32-bit ortamında dönüştürücü gibi görünür:

```
0x40000000:    jmp DWORD PTR __imp_func1
```

Burada `imp_func1` adresi `func1` .exe dosyasını içeri aktarma adres tablosunda yuvası. Bu nedenle tüm adresleri bağlayıcıya bilinir. Yükleyici, her şeyin doğru şekilde çalışması yükleme zamanında .exe dosyasının içeri aktarma adresi tablosunu güncelleştirmek yalnızca vardır.

Bu nedenle, kullanarak **__declspec(dllimport)** gerekli değilse, bağlayıcı bir dönüştürücü oluşturmaz, çünkü daha iyidir. Dönüştürücüleri kodu daha büyük hale (RISC sistemlerde, bu çok yönerge olabilir) ve, önbellek performansını düşürebilir. Bir DLL içinde işlev, derleyici bildirirseniz, onu dolaylı çağrı üretebilir.

Bu nedenle şimdi bu kodu:

```
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

Bu yönerge oluşturur:

```
call DWORD PTR __imp_func1
```

Dönüştürücü ve yoktur `jmp` yönergesi, böylece kod daha küçük ve daha hızlı.

Öte yandan, bir DLL içinde işlev çağrıları için bir dolaylı çağrı kullanmak zorunda istediğiniz değil. Bir işlevin adresi biliyorsunuzdur. Yükleme ve bir dolaylı çağrı önce bir işlevin adresini depolamak için zaman ve alan gerekli olduğundan, doğrudan arama her zaman daha hızlı ve daha küçük. Yalnızca kullanmak istediğiniz **__declspec(dllimport)** DLL dışında DLL işlevlerini çağırırken. Kullanmayın **__declspec(dllimport)** bu DLL'yi oluştururken bir DLL içinde işlevleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir Uygulamaya Aktarma](../build/importing-into-an-application.md)