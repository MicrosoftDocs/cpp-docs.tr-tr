---
description: 'Hakkında daha fazla bilgi edinin: Ileti Işleme ve komut hedefleri'
title: İleti İşleme ve Komut Hedefleri
ms.date: 11/04/2016
f1_keywords:
- IOleCommandTarget
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
ms.openlocfilehash: 35dc54687c7f3742f72d58f5c84cd274bc8fee09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203295"
---
# <a name="message-handling-and-command-targets"></a>İleti İşleme ve Komut Hedefleri

Komut gönderme arabirimi `IOleCommandTarget` komutları sorgulamak ve yürütmek için basit ve genişletilebilir bir mekanizma tanımlar. Bu mekanizma, `IDispatch` tamamen standart bir komut kümesi kullandığından ve komutların nadiren bağımsız değişkenlere sahip olduğu ve hiçbir tür bilgisinin bulunmadığı Için Otomasyon 'dan daha basit bir yöntem değildir. (tür güvenliği, komut bağımsız değişkenleri için de bu şekilde azalmaktadır).

Komut gönderme arabirimi tasarımında her komut, kendisi bir **GUID** ile tanımlanmış bir "komut grubuna" aittir. Bu nedenle, herkes yeni bir grup tanımlayabilir ve bu grup içindeki tüm komutları Microsoft veya başka bir satıcıyla koordine etmek zorunda kalmadan tanımlayabilir. (Bu temelde, Otomasyon 'daki bir **dispınterface** ve **DISPID** 'ler ile aynı tanım anlamına gelir. Burada çakışma vardır, ancak bu komut yönlendirme mekanizması yalnızca komut yönlendirmesi için olsa da, büyük ölçekte Otomasyon tutamaçları olarak betik/programlama için kullanılamaz.)

`IOleCommandTarget` aşağıdaki senaryoları işler:

- Bir nesne yerinde etkinleştirildiğinde, yalnızca nesnenin araç çubukları görüntülenir ve nesnenin araç çubuklarının **Yazdır**, **Baskı Önizleme**, **kaydetme**, **Yeni**, **Yakınlaştırma** ve diğerleri gibi bazı kapsayıcı komutlarına yönelik düğmeleri olabilir. (Yerinde etkinleştirme standartları, nesnelerin araç çubuklarından bu tür düğmeleri kaldırmasını veya en azından bunları devre dışı bırakmanızı öneririz. Bu tasarım, bu komutların etkinleştirilmesini ve henüz doğru işleyiciye yönlendirilmesini sağlar.) Şu anda nesnenin bu komutları kapsayıcıya göndermek için bir mekanizma yoktur.

- Etkin bir belge, etkin bir belge kapsayıcısına (Office Ciltçi gibi) katıştırıldığında, kapsayıcının **Yazıcı**, **sayfa kurulumu**, **Özellikler** gibi komutları ve kapsanan etkin belgeye gönderilmesi gerekebilir.

Bu basit komut yönlendirmesi, mevcut Otomasyon standartları ve aracılığıyla işlenebilir `IDispatch` . Ancak, ile ilgili ek yük `IDispatch` burada gereklidir, bu nedenle `IOleCommandTarget` aynı uçları elde etmek için daha basit bir yol sağlar:

```
interface IOleCommandTarget : IUnknown
    {
    HRESULT QueryStatus(
        [in] GUID *pguidCmdGroup,
        [in] ULONG cCmds,
        [in,out][size_is(cCmds)] OLECMD *prgCmds,
        [in,out] OLECMDTEXT *pCmdText);
    HRESULT Exec(
        [in] GUID *pguidCmdGroup,
        [in] DWORD nCmdID,
        [in] DWORD nCmdExecOpt,
        [in] VARIANTARG *pvaIn,
        [in,out] VARIANTARG *pvaOut);
    }
```

`QueryStatus`Burada yöntemi, bir **GUID** ile tanımlanmakta olan küme için belirli bir komut kümesinin desteklenip desteklenmediğini sınar. Bu çağrı, desteklenen komutların yanı sıra bir komutun adını ve/veya durum bilgilerini açıklayan metni döndüren bir **OLECMD** değeri (yapılar) dizisini doldurur. Çağıran bir komutu çağırmak istediğinde, bir geri dönüş değeri elde etmek için komutu (ve **GUID 'yi**) `Exec` Seçenekler ve bağımsız değişkenlerle birlikte geçirebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Etkin belge kapsayıcıları](active-document-containers.md)
