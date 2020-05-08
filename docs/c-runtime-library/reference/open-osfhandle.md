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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 9fbe4a4079fcbb8414e09d0f7dd814a3957e0822
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910669"
---
# <a name="_open_osfhandle"></a>_open_osfhandle

C çalışma zamanı dosya tanımlayıcısını var olan bir işletim sistemi dosya tanıtıcısı ile ilişkilendirir.

## <a name="syntax"></a>Sözdizimi

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Parametreler

*osfhandle*<br/>
İşletim sistemi dosyası tanıtıcısı.

*bayraklar*<br/>
İzin verilen işlem türleri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_open_osfhandle** bir C çalışma zamanı dosya tanımlayıcısı döndürür. Aksi takdirde,-1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_Open_osfhandle** Işlevi bir C çalışma zamanı dosya tanımlayıcısı ayırır. Bu dosya tanımlayıcısını *osfhandle*tarafından belirtilen işletim sistemi dosyası tanıtıcısı ile ilişkilendirir. Derleyici uyarısından kaçınmak için, *osfhandle* bağımsız değişkenini **tanıtıcıdan** **intptr_t**atayın. *Flags* bağımsız değişkeni, fcntl. h> içinde \<tanımlanan bir veya daha fazla bildirim sabitlerinden oluşan bir tamsayı ifadesidir. *Bayrak* bağımsız değişkenini oluşturmak için iki veya daha fazla bildirim sabiti birleştirmek için BIT düzeyinde OR işlecini ( **&#124;** ) kullanabilirsiniz.

Bu bildirim sabitleri, \<fcntl. h> tanımlanmıştır:

|||
|-|-|
| **\_O\_ekleme** | Her yazma işleminden önce dosyanın sonuna bir dosya işaretçisi konumlandırır. |
| **\_O\_yalnızca RD** | Dosyayı salt okuma için açar. |
| **\_O\_metni** | Dosyayı metin (çevrilmiş) modunda açar. |
| **\_O\_wtext** | Dosyayı Unicode (çevrilmiş UTF-16) modunda açar. |

**_Open_osfhandle** çağrısı Win32 dosya tanıtıcısının sahipliğini dosya tanımlayıcısına aktarır. **_Open_osfhandle**kullanılarak açılan bir dosyayı kapatmak için [ \_kapat](close.md)' ı çağırın. Temel alınan işletim sistemi dosya tanıtıcısı, **_close**çağrısıyla de kapatılır. Özgün tanıtıcıda, **CloseHandle** Win32 işlevini çağırmayın. Dosya tanımlayıcısının bir **dosya &#42;** akışı varsa, [fclose](fclose-fcloseall.md) çağrısı hem dosya tanımlayıcısını hem de temel alınan tanıtıcıyı kapatır. Bu durumda, özgün tanıtıcıdaki dosya tanımlayıcısında veya **CloseHandle** üzerinde **_close** çağırmayın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_open_osfhandle**|\<GÇ. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya IŞLEME](../../c-runtime-library/file-handling.md)<br/>
[\_get_osfhandle](get-osfhandle.md)
