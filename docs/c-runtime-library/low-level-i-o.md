---
title: Düşük Düzey G/Ç
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [CRT], low-level
- I/O [CRT], functions
- low-level I/O routines
- file handles [C++]
- file handles [C++], I/O functions
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
ms.openlocfilehash: acf07682e9045800bb04aa4c9d6abc5ae4376280
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443106"
---
# <a name="low-level-io"></a>Düşük Düzey G/Ç

Bu işlevler, akış g/ç tarafından sağlanenden daha düşük düzeydeki işlemler için işletim sistemini doğrudan çağırır. Düşük düzey giriş ve çıkış çağrıları arabellek veya biçimlendirme verileri değildir.

Düşük düzey yordamlar, program başlangıcında açılan standart akışlara aşağıdaki önceden tanımlanmış dosya tanımlayıcılarını kullanarak erişebilirler.

|Akış|Dosya tanımlayıcısı|
|------------|---------------------|
|**stdin**|0|
|**stdout**|1|
|**stderr**|2|

Alt düzey g/ç yordamları bir hata oluştuğunda [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) genel değişkenini ayarlar. STDIO 'ı dahil etmeniz gerekir. Yalnızca programınız STDIO 'da tanımlanan bir sabit gerektiriyorsa alt düzey işlevleri kullandığınızda H. H, dosya sonu göstergesi (**EOF**) gibi.

## <a name="low-level-io-functions"></a>Alt düzey g/ç Işlevleri

|İşlev|Kullanım|
|--------------|---------|
|[_close](../c-runtime-library/reference/close.md)|Dosyayı kapat|
|[_commit](../c-runtime-library/reference/commit.md)|Dosyayı diske Temizleme|
|[_creat, _wcreat](../c-runtime-library/reference/creat-wcreat.md)|Dosya oluştur|
|[_dup](../c-runtime-library/reference/dup-dup2.md)|Verilen dosya için bir sonraki kullanılabilir dosya tanımlayıcısını döndür|
|[_dup2](../c-runtime-library/reference/dup-dup2.md)|Verilen dosya için ikinci tanımlayıcı oluştur|
|[_eof](../c-runtime-library/reference/eof.md)|Dosya sonu için test|
|[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Dosya işaretçisini belirtilen konuma yeniden Konumlandır|
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Dosya Aç|
|[_read](../c-runtime-library/reference/read.md)|Dosyadaki verileri oku|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Dosya paylaşımı için dosya aç|
|[_tell, _telli64](../c-runtime-library/reference/tell-telli64.md)|Geçerli dosyayı al-işaretçi konumu|
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Dosya izni maskesini ayarla|
|[_write](../c-runtime-library/reference/write.md)|Verileri dosyaya yaz|

**_dup** ve **_dup2** genellikle önceden tanımlanmış dosya tanımlayıcılarını farklı dosyalarla ilişkilendirmek için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Sistem Çağrıları](../c-runtime-library/system-calls.md)<br/>
