---
title: __declspec(dllimport) Kullanarak İşlev Çağrılarını İçeri Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 1743cbba8c3046ef844f16be8e78d43c61f62606
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442513"
---
# <a name="importing-function-calls-using-__declspecdllimport"></a>__declspec(dllimport) Kullanarak İşlev Çağrılarını İçeri Aktarma

Aşağıdaki kod örneği, bir DLL 'den bir uygulamaya işlev çağrıları aktarmak için **_declspec (dllimport)** ' in nasıl kullanılacağını gösterir. `func1`, **ana** işlevi içeren. exe dosyasından ayrı bir dll içinde bulunan bir işlev olduğunu varsayalım.

**__Declspec (dllimport)** olmadan, bu kod verildiğinde:

```
int main(void)
{
   func1();
}
```

Derleyici şuna benzer bir kod üretir:

```
call func1
```

ve bağlayıcı, çağrıyı şuna benzer şekilde çevirir:

```
call 0x4000000         ; The address of 'func1'.
```

Başka bir DLL 'de `func1` varsa bağlayıcı, `func1` adresinin ne olduğunu bilmesinin bir yolu olmadığından doğrudan bunu çözemez. 16 bit ortamlarda bağlayıcı, bu kod adresini, yükleyicinin çalışma zamanında doğru adresle yayacağından,. exe dosyasındaki bir listeye ekler. 32-bit ve 64 bit ortamlarda bağlayıcı, adresi bilen bir dönüştürücü üretir. 32 bitlik bir ortamda dönüştürücü şöyle görünür:

```
0x40000000:    jmp DWORD PTR __imp_func1
```

Burada `imp_func1`. exe dosyasının içeri aktarma adresi tablosundaki `func1` yuvasının adresidir. Bu nedenle, tüm adresler bağlayıcı tarafından bilinir. Yükleyicinin, her şeyin düzgün çalışması için yükleme zamanında. exe dosyasının içeri aktarma adresi tablosunu güncelleştirmesi yeterlidir.

Bu nedenle, **__declspec (dllimport)** kullanmak daha iyidir, çünkü bağlayıcı gerekmiyorsa bir dönüştürücü oluşturmaz. Dönüştürücüler kodu daha büyük hale getirin (RıSC sistemlerinde, çeşitli yönergeler olabilir) ve önbellek performanslarını düşürebilir. Derleyiciye işlevin bir DLL 'de olduğunu söylüyorsunuz, sizin için dolaylı bir çağrı oluşturabilir.

Bu nedenle şu kod:

```
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

Bu yönergeyi üretir:

```
call DWORD PTR __imp_func1
```

Dönüştürücü yok ve `jmp` yönergesi yok, bu nedenle kod daha küçük ve daha hızlı.

Diğer taraftan, bir DLL içindeki işlev çağrıları için, dolaylı bir çağrı kullanmak zorunda olmak istemezsiniz. Bir işlevin adresini zaten öğrenmiş olabilirsiniz. Bir dolaylı çağrıdan önce işlevin adresini yüklemek ve depolamak için zaman ve boşluk gerektiğinden, doğrudan çağrı her zaman daha hızlı ve daha küçüktür. DLL işlevlerini yalnızca DLL dışından çağırırken **__declspec (dllimport)** kullanmak istersiniz. Bu DLL 'yi derlerken DLL içindeki işlevlerde **__declspec (dllimport)** kullanmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Bir Uygulamaya Aktarma](importing-into-an-application.md)
