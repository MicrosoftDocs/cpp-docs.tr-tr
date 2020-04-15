---
title: _open_osfhandle
ms.date: 4/2/2020
api_name:
- _open_osfhandle
- _o__open_osfhandle
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: 16966bedd80dc90eaa89ee46e6b633a9cf7af74f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338553"
---
# <a name="_open_osfhandle"></a>_open_osfhandle

C çalışma zamanı dosya tanımlayıcıyı varolan bir işletim sistemi dosya tanıtıcısıyla ilişkilendirin.

## <a name="syntax"></a>Sözdizimi

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Parametreler

*osfhandle*<br/>
İşletim sistemi dosya kolu.

*bayraklar*<br/>
İzin verilen işlem türleri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı _open_osfhandle c çalışma zamanı dosya **tanımlayıcısı** döndürür. Aksi takdirde , -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_open_osfhandle** işlevi C çalışma zamanı dosya tanımlayıcısı ayırır. Bu dosya tanımlayıcısını *osfhandle*tarafından belirtilen işletim sistemi dosya tutamacı ile ilişkilendirer. Derleyici uyarısını önlemek *için, OSFHandle* bağımsız değişkenini **HANDLE'dan** **intptr_t'a**atın. *Bayraklar* bağımsız değişkeni, fcntl.h> tanımlanan bir \<veya daha fazla bildirim sabitinden oluşan bir tamsayı ifadesidir. *Bayraklar* bağımsız değişkenini oluşturmak için iki veya daha fazla bildirim sabitini birleştirmek için bitwise-OR işleci **(&#124;)** kullanabilirsiniz.

Bu manifesto sabitleri \<fcntl.h> tanımlanır:

|||
|-|-|
| **\_O\_EK** | Her yazma işleminden önce bir dosya işaretçisini dosyanın sonuna yerlebir eder. |
| **\_O\_RDONLY** | Yalnızca okumak için dosyayı açar. |
| **\_O\_TEKSTİl** | Dosyayı metin (çevrilmiş) modda açar. |
| **\_O\_WTEXT** | Dosyayı Unicode (utf-16 çevirisi) modunda açar. |

çağrı **_open_osfhandle,** Win32 dosya tanıtıcısının sahipliğini dosya tanımlayıcısına aktarmaktadır. _open_osfhandle kullanarak açılan bir **dosyayı**kapatmak için [ \_kapat'ı](close.md)arayın. Altta yatan işletim sistemi dosya tutamacı da **_close**için bir çağrı ile kapatılır. Orijinal tutamacında Win32 işlevini **CloseHandle** olarak aramayın. Dosya tanımlayıcısı bir **DOSYA &#42;** akışına aitse, [fclose](fclose-fcloseall.md) çağrısı hem dosya tanımlayıcısını hem de alttaki tanıtıcıyı kapatır. Bu durumda, dosya tanımlayıcısında **_close** veya özgün tanıtıcıda **CloseHandle'ı** aramayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[\_get_osfhandle](get-osfhandle.md)
