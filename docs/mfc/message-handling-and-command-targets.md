---
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
ms.openlocfilehash: f9212e32605a1fed179c931d4f63833e17870b5c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442542"
---
# <a name="message-handling-and-command-targets"></a>İleti İşleme ve Komut Hedefleri

Komut gönderme arabirimi `IOleCommandTarget` sorgulamak ve komutları yürütmek için basit ve Genişletilebilir bir mekanizma tanımlar. Bu mekanizma, Otomasyon'un basittir `IDispatch` tamamen komutları; standart bir dizi üzerinde kullandığından komutları, bağımsız değişkenleri nadiren sahiptir ve hiçbir tür bilgileri söz konusu (komut satırı bağımsız değişkenlerini için de tür güvenliği yayınladıklarını).

Komut gönderme arabirimi tasarımında, her komut "kendisi ile tanımlanan bir komut grubuyla" ait bir **GUID**. Bu nedenle, herkesin yeni bir grup tanımlayın ve Microsoft ile koordine etmek için herhangi bir gereksinim veya diğer herhangi bir satıcı olmadan o grup içindeki tüm komutları tanımlayın. (Bu aslında aynı olduğu anlamına gelir tanımının bir **dispinterface** yanı sıra **DISPID değeri** automation'da. Var. çakışma Burada, bu komut yönlendirme mekanizması Otomasyon tanıtıcıları komut yönlendirme için yalnızca ve büyük bir ölçekte komut dosyası/programlama için olsa)

`IOleCommandTarget` Aşağıdaki senaryolarda işler:

- Bir nesne yerinde nesnenin araç çubukları genellikle görüntülenir ve nesnenin araç çubukları gibi kapsayıcı komutlardan bazıları için düğmeler olabilir yalnızca etkin olduğunda **yazdırma**, **Baskı Önizleme**,  **Kaydet**, **yeni**, **yakınlaştırma**ve diğerleri. (Kaldır nesneleri standartları önerilir yerinde etkinleştirme gibi düğmeleri araç çubuklarını, veya en az bunları devre dışı bırakın. Bu tasarım etkinleştirilmeli ve henüz doğru işleyicisine yönlendirilen için bu komutları sağlar.) Şu anda bu komutları kapsayıcıya gönderileceği nesne için bir mekanizma yoktur.

- Etkin belge (örneğin, Office Binder) bir etkin belge kapsayıcı katıştırıldığında, kapsayıcı komutları gibi göndermeniz gerekebilir **yazdırma**, **sayfa yapısı**, **özellikleri**ve diğer içerilen etkin belge için.

Bu basit bir komut yönlendirme var olan Otomasyon standartları işlenmesi ve `IDispatch`. Ancak, ek yükü ile söz konusu `IDispatch` burada gerekli olandan daha şekilde `IOleCommandTarget` aynı uçları elde etmek için basit bir yol sağlar:

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

`QueryStatus` Yöntemi burada komutları belirli bir kümesini, küme ile tanımlanmasını olup olmadığını test eder bir **GUID**, desteklenir. Bu çağrı bir dizi doldurur **OLECMD** (yapıları) değerlerle komutları yanı sıra bir komutu ve/veya durum bilgisi adını açıklayan metin döndüren desteklenen listesi. Arayan, bir komut çağrılacak istediğinde komutu geçirebilirsiniz (ve kümesi **GUID**) için `Exec` seçenekleri ve bağımsız değişkenleri yanı sıra bir dönüş değeri geri alamazsınız.

## <a name="see-also"></a>Ayrıca Bkz.

[Etkin Belge Kapsayıcıları](../mfc/active-document-containers.md)

