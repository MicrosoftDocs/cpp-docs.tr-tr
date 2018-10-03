---
title: Düşük düzey g/ç | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- I/O [CRT], low-level
- I/O [CRT], functions
- low-level I/O routines
- file handles [C++]
- file handles [C++], I/O functions
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8134ea416f94def7e985a4d63cc61d740924317a
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235301"
---
# <a name="low-level-io"></a>Düşük Düzey G/Ç

Bu işlevler doğrudan akış g/ç tarafından sağlanan daha düşük düzeyli işlem için işletim sistemi çağırın. Alt düzey giriş ve çıkış çağrılar yapmak arabellek veya biçim verileri.

Alt düzey yordamlar aşağıdaki önceden tanımlanmış dosya tanımlayıcıları kullanarak program başlangıcında açılmış olan bir standart akış erişebilirsiniz.

|Akış|Dosya tanımlayıcısı|
|------------|---------------------|
|**Stdin**|0|
|**STDOUT**|1.|
|**stderr**|2|

Düşük düzey g/ç rutinleri kümesi [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bir hata oluştuğunda genel değişkeni. STDIO eklemeniz gerekir. Yalnızca programınız STDIO içinde tanımlanmış bir sabit gerektiriyorsa, düşük düzeyli işlevleri kullandığınızda H. Dosya sonu göstergesi gibi H (**EOF**).

## <a name="low-level-io-functions"></a>Düşük düzey g/ç işlevleri

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[_close](../c-runtime-library/reference/close.md)|Dosyayı Kapat|
|[_commit](../c-runtime-library/reference/commit.md)|Disk dosyası temizleme|
|[_creat, _wcreat](../c-runtime-library/reference/creat-wcreat.md)|Dosya oluşturma|
|[_dup](../c-runtime-library/reference/dup-dup2.md)|Sonraki kullanılabilir dosya tanımlayıcısını dönüş verilen dosya|
|[_dup2](../c-runtime-library/reference/dup-dup2.md)|Belirtilen ikinci tanımlayıcısı oluşturun dosyası|
|[_eof](../c-runtime-library/reference/eof.md)|Dosya sonu için sınama|
|[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Yeniden konumlandırma dosya işaretçisi konumunu verilen|
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Dosya Aç|
|[_read](../c-runtime-library/reference/read.md)|Dosyasından veri okuma|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Dosya Paylaşımı için Dosya Aç|
|[_tell, _telli64](../c-runtime-library/reference/tell-telli64.md)|Geçerli dosya işaretçisi konumunu alma|
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Dosya izin maske ayarlama|
|[_write](../c-runtime-library/reference/write.md)|Dosyasına veri yazma|

**_dup** ve **_dup2** genellikle önceden tanımlanmış dosya tanımlayıcıları farklı dosya ile ilişkilendirmek için kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Sistem Çağrıları](../c-runtime-library/system-calls.md)<br/>
