---
title: Bildirim Kancaları
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
ms.openlocfilehash: 884d8e8479b7cad28d99e19adfac4d05dbeec5f5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818316"
---
# <a name="notification-hooks"></a>Bildirim Kancaları

Bildirim kancaları yalnızca aşağıdaki eylemleri Yardımcısı yordamı gerçekleştirmeden önce çağrılır:

- Kitaplığa depolanmış tanıtıcı, önceden yüklenip yüklenmediğini görmek için denetlenir.

- **LoadLibrary** dll yükleme girişiminde çağrılır.

- **GetProcAddress** yordamı adresini alma girişimi için çağrılır.

- Dönüş gecikmesi içeri aktarmak için dönüştürücü yükleyin.

Bildirim kanca etkinleştirilir:

- Yeni bir tanımı işaretçinin sağlama tarafından **__pfnDliNotifyHook2** bildirimleri alan kendi işlevine işaret edecek şekilde başlatılır.

   \-veya -

- İşaretçi ayarlayarak **__pfnDliNotifyHook2** kanca işlevinize yükleme çağrıları program DLL gecikme önce.

Bildirim ise **dliStartProcessing**, kanca işlevini döndürebilir:

- NULL

   Varsayılan Yardımcısı DLL'in yüklenmesini işler. Bu, yalnızca bilgilendirici amaçlarla çağrılacak kullanışlıdır.

- İşlev işaretçisi

   Varsayılan gecikme yükü boşaltma atlama. Bu, kendi yük işleyici sağlamanıza olanak tanır.

Bildirim ise **dliNotePreLoadLibrary**, kanca işlevini döndürebilir:

- yalnızca bir bilgi bildirimleri istiyorsa, 0.

- HModule'ü DLL yüklerse yüklenen DLL için.

Bildirim ise **dliNotePreGetProcAddress**, kanca işlevini döndürebilir:

- yalnızca bir bilgi bildirimleri istiyorsa, 0.

- Kanca işlevini adresi alırsa içeri aktarılan bir işlevin adresi.

Bildirim ise **dliNoteEndProcessing**, kanca işlevin dönüş değeri yok sayılır.

This işaretçisi (sıfırdan farklı) başlatılırsa, gecikme yük yardımcı yürütme boyunca belirli bir bildirim noktalarda işlevi çağırır. İşlev işaretçisi aşağıdaki tanımları içerir:

```C
// The "notify hook" gets called for every call to the
// delay load helper.  This allows a user to hook every call and
// skip the delay load helper entirely.
//
// dliNotify == {
//  dliStartProcessing |
//  dliNotePreLoadLibrary  |
//  dliNotePreGetProc |
//  dliNoteEndProcessing}
//  on this call.
//
ExternC
PfnDliHook   __pfnDliNotifyHook2;

// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

Bildirimleri geçirin bir **DelayLoadInfo** bildirim değerin yanı sıra kanca işlevini yapısına. Bu veriler, gecikme yük yardımcı yordamı tarafından kullanılmak için aynıdır. Bildirim değeri içinde tanımlanan değerlerden olacaktır [yapı ve sabit tanımları](structure-and-constant-definitions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme ve Bildirme](error-handling-and-notification.md)
