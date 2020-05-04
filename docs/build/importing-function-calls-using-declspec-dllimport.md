---
title: __declspec(dllimport) kullanarak işlev çağrılarını içeri aktarma
description: DLL verileri ve işlevleri çağrılırken __declspec (dllimport) nasıl ve neden kullanılır.
ms.date: 05/03/2020
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 515fbdb2824c1eaf41e822adeae1a16d3072eec4
ms.sourcegitcommit: 8a01ae145bc65f5bc90d6e47b4a1bdf47b073ee7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82765727"
---
# <a name="importing-function-calls-using-__declspecdllimport"></a>Kullanarak işlev çağrıları içeri aktarılıyor`__declspec(dllimport)`

Kullanarak çağrılara açıklama ekleme, **`__declspec(dllimport)`** bunları daha hızlı hale getirir. **`__declspec(dllimport)`**, her zaman, aktarılmış DLL verilerine erişmek için gereklidir.

## <a name="import-a-function-from-a-dll"></a>DLL 'den bir işlev içeri aktarma

Aşağıdaki kod örneği, bir DLL 'den bir **`__declspec(dllimport)`** uygulamaya işlev çağrıları aktarmak için nasıl kullanılacağını gösterir. Bu `func1` işlevin, **ana** işlevi içeren YÜRÜTÜLEBILIR dosyadan ayrı bir dll 'de olduğunu varsayalım.

Olmadan **`__declspec(dllimport)`**, bu kod verildiğinde:

```C
int main(void)
{
   func1();
}
```

Derleyici şuna benzer bir kod üretir:

```asm
call func1
```

ve bağlayıcı, çağrıyı şuna benzer şekilde çevirir:

```asm
call 0x4000000         ; The address of 'func1'.
```

`func1` Başka bir dll 'de varsa bağlayıcı, adresi ne `func1` olduğunu bilmenin bir yolu olmadığından, bu adresi doğrudan çözemez. 32-bit ve 64 bit ortamlarda bağlayıcı, bilinen bir adreste dönüştürücü oluşturur. 32 bitlik bir ortamda dönüştürücü şöyle görünür:

```asm
0x40000000:    jmp DWORD PTR __imp_func1
```

`__imp_func1` Bu, yürütülebilir dosyanın içeri aktarma `func1` adresi tablosundaki yuvanın adresidir. Tüm bu adresler bağlayıcı tarafından bilinir. Yükleyicinin, her şeyin düzgün çalışması için yükleme zamanında yürütülebilir dosyanın içeri aktarma adresi tablosunu güncelleştirmesi yeterlidir.

Bu nedenle kullanılması **`__declspec(dllimport)`** daha iyidir: bağlayıcı gerekmiyorsa bir dönüştürücü oluşturmadığından. Dönüştürücüler kodu daha büyük hale getirin (RıSC sistemlerinde, çeşitli yönergeler olabilir) ve önbellek performanslarını düşürebilir. Derleyiciye işlevin bir DLL 'de olduğunu söylüyorsunuz, sizin için dolaylı bir çağrı oluşturabilir.

Bu nedenle şu kod:

```C
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

Bu yönergeyi üretir:

```asm
call DWORD PTR __imp_func1
```

Dönüştürücü ve `jmp` yönerge yoktur, bu nedenle kod daha küçük ve daha hızlıdır. Ayrıca, tüm program iyileştirmesini kullanarak aynı **`__declspec(dllimport)`** etkiyi de alabilirsiniz. Daha fazla bilgi için bkz. [/GL (tüm program iyileştirmesi)](reference/gl-whole-program-optimization.md).

DLL içindeki işlev çağrıları için dolaylı bir çağrı kullanmak istemezsiniz. Bağlayıcı zaten işlevin adresini biliyor. Bir dolaylı çağrıdan önce işlevin adresini yüklemek ve depolamak için ek zaman ve alan alır. Doğrudan çağrı her zaman daha hızlı ve daha küçüktür. Yalnızca DLL işlevlerini DLL dışından **`__declspec(dllimport)`** çağırırken kullanmak istiyorsunuz. Bu DLL **`__declspec(dllimport)`** 'YI derlerken dll içindeki işlevlerde kullanmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Bir Uygulamaya Aktarma](importing-into-an-application.md)
