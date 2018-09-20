---
title: Program aracılığıyla yazdırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 527ecd89838702a3ec8a91c35e67c1c0cc26501e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397844"
---
# <a name="programmatic-printing"></a>Program Aracılığıyla Yazdırma

OLE sağlanan kalıcı belgeleri benzersiz olarak tanımlanabilmesi için anlamına gelir (`GetClassFile`) ve bunları kendi ilişkili koda yük (`CoCreateInstance`, `QueryInterface(IID_IPersistFile)`, `QueryInterface(IID_IPersistStorage)`, `IPersistFile::Load`, ve `IPersistStorage::Load`). Etkin belge kapsaması (OLE 2.0 ilk olarak gönderilmeyen varolan bir OLE tasarımı kullanarak) daha fazla yazdırma belgeleri etkinleştirmek için bir temel standart yazdırma arabirimi tanıtır `IPrint`, yükleyebilir ve herhangi bir nesne üzerinden kullanıma sunuldu kalıcı durum belge türü. Her bir etkin belge görünümü isteğe bağlı olarak destekleyebilir `IPrint` bu yetenekleri sağlamak için arabirim.

`IPrint` Arabirimi şu şekilde tanımlanır:

```
interface IPrint : IUnknown
    {
    HRESULT SetInitialPageNum([in] LONG nFirstPage);
    HRESULT GetPageInfo(
        [out] LONG *pnFirstPage,
        [out] LONG *pcPages);
    HRESULT Print(
        [in] DWORD grfFlags,
        [in,out] DVTARGETDEVICE **pptd,
        [in,out] PAGESET ** ppPageSet,
        [in,out] STGMEDIUM **ppstgmOptions,
        [in] IContinueCallback* pCallback,
        [in] LONG nFirstPage,
        [out] LONG *pcPagesPrinted,
        [out] LONG *pnPageLast);
    };
```

İstemcileri ve kapsayıcıları kullanmanız yeterlidir `IPrint::Print` belgenin belge yüklendiğinde yazdırma denetim bayrakları, hedef cihaz, yazdırmak için sayfaları belirtme IOleCommandTarget komutunu almasını ve ek seçenekler. İstemci arabirimi yoluyla yazdırma devamlılık de denetleyebilirsiniz `IContinueCallback` (aşağıya bakın).

Ayrıca, `IPrint::SetInitialPageNum` bir numaralandırma sorunsuz bir şekilde, açıkça için etkin belge kapsayıcıları Office Binder gibi bir avantajı sayfaları gibi bir dizi belgeleri yazdırma özelliğini destekler. `IPrint::GetPageInfo` Başlangıç almak çağırıcı sağlayarak basit sayfalandırma bilgileri görüntüleme yapar sayfa numarası daha önce geçirilen `SetInitialPageNum` (veya belgenin iç varsayılan başlangıç sayfa numarası) ve belgedeki sayfa sayısı.

Nesneleri destekleyen `IPrint` kayıt defterinde nesnenin CLSID altında depolanan "Printable" anahtarı ile işaretlenir:

HKEY_CLASSES_ROOT\CLSID\\{...} \Printable

`IPrint` genellikle ya da destekleyen aynı nesne üzerinde uygulanan `IPersistFile` veya `IPersistStorage`. Çağıranlar "Printable" anahtarı için kayıt defterinde bakarak bazı sınıfı kalıcı durumunu program aracılığıyla yazdırma olanağı unutmayın. Şu anda "Yazdırılabilir" desteği için en az gösterir `IPrint`; diğer arabirimleri, ardından aracılığıyla kullanılabilirdi gelecekte tanımlanabilir `QueryInterface` burada `IPrint` yalnızca temel düzeyde desteği temsil eder.

Yazdırma işlemi sırasında istemci veya yazdırma devam denetlemek için yazdırma başlatılan kapsayıcı isteyebilirsiniz. Örneğin, kapsayıcı, yazdırma işi olabildiğince çabuk sonlandırması gerektiğini "yazdırma Durdur" komutu destekleyebilir. Bu özelliği desteklemek için istemci yazdırılabilir bir nesnenin küçük bildirim havuz nesnesiyle arabirimi uygulayabilir `IContinueCallback`:

```
interface IContinueCallback : IUnknown
    {
    HRESULT FContinue(void);
    HRESULT FContinuePrinting(
        [in] LONG cPagesPrinted,
        [in] LONG nCurrentPage,
        [in] LPOLESTR pszPrintStatus);
    };
```

Bu arabirim Win32 API çeşitli devamlılık yordamlarda yer alan genel devamlılık geri çağırma işlevi olarak yararlı olacak şekilde tasarlanmıştır (gibi `AbortProc` yazdırma ve `EnumMetafileProc` meta sabit listesi için). Bu nedenle bu arabirimi tasarımı çok çeşitli uzun süren işlemlerin yararlı olur.

En genel durumlarda `IContinueCallback::FContinue` işlevi düzenli aralıklarla uzun herhangi bir işlem tarafından çağrılır. Havuz nesneyi S_OK işleme devam etmek ve yordamı olabildiğince çabuk durdurmak için S_FALSE döndürür.

`FContinue`, ancak bağlamında kullanılmaz `IPrint::Print`; bunun yerine, kullandığı yazdırma `IContinueCallback::FContinuePrint`. Herhangi bir yazdırma nesnesi düzenli aralıklarla çağırmalıdır `FContinuePrinting` yazdırma sayfa sayısı, yazdırılmasını sayfa numarası ve istemci (örneğin, "sayfası kullanıcıya tercih edebilirsiniz yazdırma durumunu açıklayan bir ek dize geçirme 5 / 19").

## <a name="see-also"></a>Ayrıca Bkz.

[Etkin Belge Kapsayıcıları](../mfc/active-document-containers.md)

