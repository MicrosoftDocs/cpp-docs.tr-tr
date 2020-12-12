---
description: 'Daha fazla bilgi edinin: bildirim kancaları'
title: Bildirim Kancaları
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
ms.openlocfilehash: 716d2b31faa71c77ec436662ce00368d15afc4b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209756"
---
# <a name="notification-hooks"></a>Bildirim Kancaları

Bildirim kancaları, yardım yordamında aşağıdaki eylemler yapılmadan hemen önce çağırılır:

- Kitaplığın saklı tanıtıcısı, zaten yüklenmiş olup olmadığını görmek üzere denetlenir.

- DLL 'nin yükünü denemek için **LoadLibrary** çağırılır.

- **GetProcAddress** , yordamın adresini almayı denemek için çağrılır.

- Gecikmeli içeri aktarma yükleme Dönüştürücüsü ' ne dönün.

Bildirim kancası etkin:

- İşaretçiyi, bildirimleri alan kendi işlevinizi işaret etmek üzere başlatılan **__pfnDliNotifyHook2** işaretçinin yeni bir tanımını sunarak.

   \-veya

- İşaretçiyi, DLL 'ye yapılan herhangi bir çağrının yükleme gecikmesi olan herhangi bir çağrısından önce kanca işlevinizi **__pfnDliNotifyHook2** ayarlayarak.

Bildirim **dliStartProcessing** ise, kanca işlevi şu şekilde dönebilir:

- NULL

   Varsayılan yardımcı, DLL yüklemesini işler. Bu, yalnızca bilgilendirme amacıyla çağrılabilmesi için kullanışlıdır.

- işlev işaretçisi

   Varsayılan Gecikmeli yükleme işlemesini atlayın. Bu, kendi yük işleyicinizi sağlamanıza olanak tanır.

Bildirim **dliNotePreLoadLibrary** ise, kanca işlevi şu şekilde dönebilir:

- yalnızca bilgilendirme bildirimleri istiyorsa 0.

- DLL kendisini yükleirse yüklenen DLL için HMODULE.

Bildirim **dliNotePreGetProcAddress** ise, kanca işlevi şu şekilde dönebilir:

- yalnızca bilgilendirme bildirimleri istiyorsa 0.

- Kanca işlevi adresin kendisini alırsa, içeri aktarılan işlevin adresi.

Bildirim **dliNoteEndProcessing** ise, kanca işlevinin dönüş değeri yok sayılır.

Bu işaretçi başlatılmışsa (sıfır dışında), gecikme Yükleme Yardımcısı, işlevini yürütme boyunca belirli bildirim noktalarında çağırır. İşlev işaretçisi aşağıdaki tanıma sahiptir:

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

Bildirimler bir **DelayLoadInfo** yapısını, bildirim değeriyle birlikte kanca işlevine iletir. Bu veriler, gecikme Yükleme Yardımcısı yordamının kullandığı ile aynıdır. Bildirim değeri, [Yapı ve sabit tanımlarda](structure-and-constant-definitions.md)tanımlanan değerlerden biri olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Işleme ve bildirim](error-handling-and-notification.md)
