---
title: CL komut dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8458462304a9b739c61997505724d21bb56763f6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708677"
---
# <a name="cl-command-files"></a>CL Komut Dosyaları

Bir komut dosyası seçenekleri ve aksi takdirde yazarsınız üzerinde dosya adlarını içeren bir metin dosyasıdır [komut satırı](../../build/reference/compiler-command-line-syntax.md) veya belirtmeyi [CL ortam değişkeninde](../../build/reference/cl-environment-variables.md). CL derleyici komut dosyası CL ortam değişkeninde veya komut satırında bir bağımsız değişken olarak kabul eder. Komut satırında veya CL ortam değişkeninde olanın aksine, komut dosyası birden fazla satırı seçeneği ve dosya adı kullanmanıza izin verir.

Seçenekler ve dosya adları, komut dosyası CL ortam değişkeninde veya komut satırında bir komut dosya konumuna göre işlenir. Bununla birlikte, / Link seçeneği komut dosyasında görünüyorsa, satırın geri kalanını tüm seçenekleri bağlayıcıya geçirilir. Yine de sonraki satırlarında komut dosyası ve sonra komut dosyasını çağırma seçeneklerini komut satırında derleyici seçeneği olarak kabul edilir. Seçenekleri sırası yorumları nasıl etkilediği hakkında daha fazla bilgi için bkz. [CL seçenekleri sırası](../../build/reference/order-of-cl-options.md).

Bir komut dosyası CL komut içermemelidir. Her seçeneği başlamalı ve bitmelidir aynı satırda; ters eğik çizgi kullanılamaz (**\\**) iki satırı seçeneği birleştirmek için.

Bir komut dosyası tarafından belirtilen bir at işareti (**\@**) tarafından bir dosya adı; ardından dosya adı, mutlak veya göreli bir yol belirtebilirsiniz.

Örneğin, aşağıdaki komutu yanıt adındaki bir dosyada ise:

```
/Og /link LIBC.LIB
```

ve aşağıdaki CL komutu belirtin:

```
CL /Ob2 @RESP MYAPP.C
```

CL komutu aşağıdaki gibidir:

```
CL /Ob2 /Og MYAPP.C /link LIBC.LIB
```

Komut satırını ve komut dosyalı komutlar etkili bir şekilde birleştirilir unutmayın.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)