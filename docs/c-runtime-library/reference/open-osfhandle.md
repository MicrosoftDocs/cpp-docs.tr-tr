---
title: _open_osfhandle
ms.date: 05/21/2019
apiname:
- _open_osfhandle
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: 8527dade37f20b7341d5a26f5752ece668ab7fc9
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174794"
---
# <a name="openosfhandle"></a>_open_osfhandle

C çalışma zamanı dosya tanımlayıcısı, var olan bir işletim sistemi dosya tanıtıcısı ile ilişkilendirir.

## <a name="syntax"></a>Sözdizimi

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Parametreler

*osfhandle*<br/>
İşletim sistemi dosya tanıtıcısı.

*bayrakları*<br/>
İzin verilen işlem türleri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_open_osfhandle** C çalışma zamanı dosya tanımlayıcısını döndürür. Aksi takdirde, -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_Open_osfhandle** işlevi C çalışma zamanı dosya tanımlayıcısı ayırır ve tarafından belirtilen işletim sistemi dosya tanıtıcısı ile ilişkilendirir *osfhandle*. Derleyici Uyarısı önlemek için cast *osfhandle* bağımsız değişkeninden **İŞLEMEK** için **intptr_t**. *Bayrakları* değişkeni birinden oluşturulmuş bir tamsayı ifade veya daha fazla bildirim sabitleri içinde tanımlanan \<fcntl.h >. İki veya daha fazla bildirim sabitleri için form kullanılan zaman *bayrakları* bağımsız değişkeni, sabitleri, bit düzeyinde OR işleci ile birleştirilir ( **&#124;** ).

Bu bildirim sabitleri tanımlanan \<fcntl.h >:

|||
|-|-|
| **\_O\_EKLEME** | Dosya işaretçisi her yazma işleminden önce dosyanın sonuna konumlandırır. |
| **\_O\_RDONLY** | Yalnızca okuma dosyasını açar. |
| **\_O\_METİN** | Dosya, metin (çevrilmiş) modunda açılır. |
| **\_O\_WTEXT** | Dosya Unicode (çevrilmiş UTF-16) modunda açılır. |

**_Open_osfhandle** çağrı dosya tanımlayıcısı için Win32 dosya işleci sahipliğini aktarır. Kullanarak açılan bir dosyanın kapatmak için **_open_osfhandle**, çağrı [ \_kapatmak](close.md). Temel işletim sistemi dosya tanıtıcısı aynı zamanda yapılan bir çağrıyla kapalı **_close**. Win32 işlevini çağırmayın **CloseHandle** özgün tutamacı. Dosya tanımlayıcısı aitse bir **dosya &#42;**  stream ve ardından bir çağrı [fclose](fclose-fcloseall.md) üzerindeki **dosya &#42;**  dosya tanımlayıcısı ve temel akışı kapatır tanıtıcı. Bu durumda, Remove() çağırmayın **_close** üzerinde dosya tanımlayıcısı veya **CloseHandle** özgün tutamacı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
