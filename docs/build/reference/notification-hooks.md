---
description: 'Daha fazla bilgi edinin: Yük bildirimi kancalarını geciktir'
title: Bildirim kancaları
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.openlocfilehash: 401ae9099afcf00dc280bb4f9e5f7016a4cbc640
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667532"
---
# <a name="notification-hooks"></a>Bildirim kancaları

Gecikme yükü bildirim kancaları, aşağıdaki eylemler yardımcı yordamında alınmadan hemen önce çağrılır:

- Kitaplığın saklı tanıtıcısı, zaten yüklenmiş olup olmadığını görmek üzere denetlenir.

- `LoadLibrary` , DLL 'nin yükünü denemek için çağırılır.

- `GetProcAddress` yordamın adresini almayı denemek için çağırılır.

- Gecikmeli içeri aktarma yükleme Dönüştürücüsü ' ne dönün.

Bildirim kancası etkin:

- Bir işaretçinin, `__pfnDliNotifyHook2` bildirimleri alan kendi işlevinizi işaret etmek üzere başlatılmış yeni bir tanımını sağlayarak.

   \-veya

- İşaretçiyi, `__pfnDliNotifyHook2` DLL 'ye yapılan herhangi bir çağrının yükleme gecikmesi olduğu herhangi bir çağrısından önce kanca işleviniz olarak ayarlayarak.

Bildirim ise `dliStartProcessing` , kanca işlevi şu şekilde dönebilir:

- `NULL`

   Varsayılan yardımcı, DLL yüklemesini işler. Yalnızca bilgilendirme amacıyla çağırmak yararlı olur.

- bir işlev işaretçisi

   Varsayılan Gecikmeli yükleme işlemesini atlayın. Kendi yük işleyicinizi sağlamanıza olanak tanır.

Bildirim ise `dliNotePreLoadLibrary` , kanca işlevi şu şekilde dönebilir:

- yalnızca bilgilendirme bildirimleri istiyorsa 0.

- `HMODULE`Yüklenen dll için, DLL kendisini yükleirse.

Bildirim ise `dliNotePreGetProcAddress` , kanca işlevi şu şekilde dönebilir:

- yalnızca bilgilendirme bildirimleri istiyorsa 0.

- Kanca işlevi adresin kendisini alırsa, içeri aktarılan işlevin adresi.

Bildirim ise `dliNoteEndProcessing` , kanca işlevinin dönüş değeri yok sayılır.

Bu işaretçi başlatılmışsa (sıfır dışında), Gecikmeli Yükleme Yardımcısı işlevi, yürütme boyunca belirli bildirim noktalarında çağırır. İşlev işaretçisi aşağıdaki tanıma sahiptir:

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

Bildirimler, `DelayLoadInfo` bildirim değeriyle birlikte kanca işlevine bir yapıda geçer. Bu veriler, gecikme Yükleme Yardımcısı yordamının kullandığı verilerle aynıdır. Bildirim değeri, [Yapı ve sabit tanımlarda](structure-and-constant-definitions.md)tanımlanan değerlerden biri olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Hata işleme ve bildirme](error-handling-and-notification.md)
