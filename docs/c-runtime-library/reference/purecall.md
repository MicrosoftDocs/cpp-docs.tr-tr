---
title: _purecall
ms.date: 11/04/2016
api_name:
- _purecall
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
ms.openlocfilehash: 5d62ec30731ce26c4683afc88474d4bddb63a697
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950163"
---
# <a name="_purecall"></a>_purecall

Varsayılan saf sanal işlev çağırma hatası işleyicisi. Derleyici, bir saf sanal üye işlevi çağrıldığında bu işlevi çağırmak için kod üretir.

## <a name="syntax"></a>Sözdizimi

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Açıklamalar

**_Pugeri çağırma** işlevi, Microsoft C++ derleyicisinin Microsoft 'a özgü bir uygulama ayrıntısıyla belirlenir. Bu işlevin kodunuz tarafından doğrudan çağrılması amaçlanmamıştır ve genel üstbilgi bildirimi yoktur. C çalışma zamanı kitaplığının Genel dışarı aktardığı için burada belgelenmiştir.

Saf sanal işleve yapılan bir çağrı, bir uygulamaya sahip olmadığı için bir hatadır. Derleyici, bir saf sanal işlev çağrıldığında **_puhatırlayın** hata işleyicisi işlevini çağırmak için kod üretir. Varsayılan olarak, **_puhatırla** programı sonlandırır. Sonlandırmadan önce, **_pucallfunction** , işlem için ayarlanmış bir **_purecall_handler** işlevini çağırır. Hata ayıklama veya raporlama amaçlarıyla yakalamak için, saf sanal işlev çağrıları için kendi hata işleyicisi işlevinizi yükleyebilirsiniz. Kendi hata işleyicinizi kullanmak için, **_purecall_handler** imzasına sahip bir işlev oluşturun ve ardından [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) kullanarak geçerli işleyiciyi yapın.

## <a name="requirements"></a>Gereksinimler

**_Puhatırlayın** işlevinin bir üst bilgi bildirimi yok. **_Purecall_handler** typedef, \<Stdlib. h > tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
