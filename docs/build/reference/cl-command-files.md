---
title: CL Komut Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
ms.openlocfilehash: 1dc2d6bffe4d0681a04b875383215a0bbfc1a720
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440256"
---
# <a name="cl-command-files"></a>CL Komut Dosyaları

Komut dosyası, Seçenekler ve dosya türlerini içeren bir metin dosyasıdır ve aksi takdirde [komut satırına](compiler-command-line-syntax.md) yazabilir veya [CL ortam değişkenini](cl-environment-variables.md)kullanarak belirtebilirsiniz. CL, bir derleyici komut dosyasını CL ortam değişkeninde veya komut satırında bir bağımsız değişken olarak kabul eder. Komut satırında veya CL ortam değişkeninde olanın aksine, komut dosyası birden fazla satırı seçeneği ve dosya adı kullanmanıza izin verir.

Bir komut dosyasındaki seçenekler ve dosya adları, CL ortam değişkeni veya komut satırı içindeki bir komut dosyası dosyasının konumuna göre işlenir. Ancak, komut dosyasında/Link seçeneği görünürse, satırdaki geri kalan tüm seçenekler bağlayıcıya geçirilir. Komut dosyasında sonraki satırlardaki seçenekler ve komut dosyası çağırma sonrasında komut satırındaki seçenekler, derleyici seçenekleri olarak kabul edilir. Seçeneklerin sırasının yorumu nasıl etkilediği hakkında daha fazla bilgi için, bkz. [cl seçenekleri sırası](order-of-cl-options.md).

Bir komut dosyası CL komutunu içermemelidir. Her seçeneğin aynı satırda başlaması ve bitmesi gerekir; iki satır arasında bir seçeneği birleştirmek için ters eğik çizgi ( **\\** ) kullanamazsınız.

Bir komut dosyası bir at işareti ( **\@** ) ve ardından bir dosya adı tarafından belirtilir; dosya adı mutlak veya göreli bir yol belirtebilir.

Örneğin, aşağıdaki komut, yanıt adlı bir dosya içinde ise:

```
/Og /link LIBC.LIB
```

ve aşağıdaki CL komutunu belirtirsiniz:

```
CL /Ob2 @RESP MYAPP.C
```

CL komutu aşağıdaki gibidir:

```
CL /Ob2 /Og MYAPP.C /link LIBC.LIB
```

Komut satırı ve komut dosyası komutlarının etkin bir şekilde birleştirildiğine unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)
