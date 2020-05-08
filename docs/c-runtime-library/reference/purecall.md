---
title: _purecall
ms.date: 4/2/2020
api_name:
- _purecall
- _o__purecall
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: 19ad6c2f517d9ddf277a7bdda6e46c7940f0d3f1
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913337"
---
# <a name="_purecall"></a>_purecall

Varsayılan saf sanal işlev çağırma hatası işleyicisi. Derleyici, bir saf sanal üye işlevi çağrıldığında bu işlevi çağırmak için kod üretir.

## <a name="syntax"></a>Sözdizimi

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Açıklamalar

**_Purecall** işlevi, Microsoft C++ derleyicisinin Microsoft 'a özgü bir uygulama ayrıntısıyla belirlenir. Bu işlevin kodunuz tarafından doğrudan çağrılması amaçlanmamıştır ve genel üstbilgi bildirimi yoktur. C çalışma zamanı kitaplığının Genel dışarı aktardığı için burada belgelenmiştir.

Saf sanal işleve yapılan bir çağrı, bir uygulamaya sahip olmadığı için bir hatadır. Derleyici, bir saf sanal işlev çağrıldığında **_purecall** hata işleyicisi işlevini çağırmak için kod üretir. Varsayılan olarak, **_purecall** programı sonlandırır. Sonlandırmadan önce, **_purecall** işlevi işlem için ayarlandıysa bir **_purecall_handler** işlevi çağırır. Hata ayıklama veya raporlama amaçlarıyla yakalamak için, saf sanal işlev çağrıları için kendi hata işleyicisi işlevinizi yükleyebilirsiniz. Kendi hata işleyicinizi kullanmak için, **_purecall_handler** imzaya sahip bir işlev oluşturun ve sonra geçerli işleyici yapmak için [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

**_Purecall** işlevinin üst bilgi bildirimi yok. **_Purecall_handler** typedef, Stdlib. \<h> içinde tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
