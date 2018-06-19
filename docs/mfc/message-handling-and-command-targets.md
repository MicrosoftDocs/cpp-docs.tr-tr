---
title: İleti işleme ve komut hedefleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7184a6e8df67dfd220173c42bfa3e0580bd2cd3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349473"
---
# <a name="message-handling-and-command-targets"></a>İleti İşleme ve Komut Hedefleri
Komut gönderme arabirimi `IOleCommandTarget` sorgulamak ve komutları yürütmek için basit ve Genişletilebilir bir mekanizma tanımlar. Bu mekanizma Otomasyonu'nun basittir `IDispatch` tamamen komutları; standart kümesinde kullandığından komutları nadiren sahip bağımsız değişkenler ve hiçbir tür bilgileri söz konusu (de komut bağımsız değişkenleri için tür güvenliği yayınladıklarını).  
  
 Komut gönderme arabirimi tasarımında, her komutun "kendisi ile tanımlanan bir komut grubuna" ait bir **GUID**. Bu nedenle, herkesin yeni bir grup tanımlayın ve Microsoft ile koordine etmek için tüm ihtiyacını veya başka bir satıcının olmadan bu gruptaki tüm komutları tanımlayın. (Bu temelde aynı tanımının araçtır bir **görüntüleme arabirimi** artı **DISPID değerleri** Otomasyon. Var. çakışma Burada, bu komut yönlendirme mekanizması Otomasyon tanıtıcıları yalnızca komut yönlendirme için değil de büyük bir ölçekte komut dosyası/programlamasına olsa)  
  
 `IOleCommandTarget` Aşağıdaki senaryolarda işler:  
  
-   Bir nesne yerinde yalnızca nesnenin araç çubukları genellikle görüntülenir ve nesnenin araç çubukları gibi kapsayıcı komutları bazıları için düğmeler olabilir etkinleştirilmiş olduğunda **yazdırma**, **Baskı Önizleme**,  **Kaydet**, `New`, **yakınlaştırma**ve diğerleri. (Kaldır nesneleri standartları önerilir yerinde etkinleştirme gibi düğmeleri araç çubuklarını veya en az bunları devre dışı bırakın. Bu tasarım etkinleştirilmeli ve henüz sağ işleyicisine yönlendirilen için bu komutları sağlar.) Şu anda, bu komutları kapsayıcısı gönderilmesi nesne için hiçbir mekanizması yoktur.  
  
-   Etkin belge (örneğin, Office Binder) bir active belge kapsayıcısındaki katıştırıldığında kapsayıcı komutları gibi göndermeniz gerekebilir **yazdırma**, **sayfa yapısı**, **özellikleri**ve içerdiği etkin belgeyi başkalarına.  
  
 Bu basit komut yönlendirme var olan Otomasyon standartları işlenmesi ve `IDispatch`. Ancak, ek yükü ile söz konusu `IDispatch` Burada, gerekli olandan daha fazla olduğu için `IOleCommandTarget` aynı uçları elde etmek için basit bir yol sağlar:  
  
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
  
 `QueryStatus` Yöntemini burada belirli bir komut kümesi, kümesi ile tanımlanmasını olup olmadığını sınar bir **GUID**, desteklenir. Bu çağrı bir dizi doldurur **OLECMD** komutları yanı sıra bir komut ve/veya durum bilgisi adını tanımlayan bir metin döndüren desteklenen listesiyle değerleri (yapıları). Çağıran bir komutunu Çağır istediğinde komutu geçirebilirsiniz (ve kümesi **GUID**) için **Exec** seçenekleri ve bağımsız değişkenleri ile birlikte bir dönüş değeri geri alamazsınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin Belge Kapsayıcıları](../mfc/active-document-containers.md)

