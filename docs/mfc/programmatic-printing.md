---
description: 'Daha fazla bilgi edinin: programlı yazdırma'
title: Program Aracılığıyla Yazdırma
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
ms.openlocfilehash: c97a3938a97970e1479add4f62b68250845ba7e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154701"
---
# <a name="programmatic-printing"></a>Program Aracılığıyla Yazdırma

OLE, kalıcı belgeleri () benzersiz bir şekilde tanımlamak `GetClassFile` ve bunları ilişkili kodlarına (,,, `CoCreateInstance` `QueryInterface(IID_IPersistFile)` `QueryInterface(IID_IPersistStorage)` `IPersistFile::Load` , ve `IPersistStorage::Load` ) yüklemek için Araçlar sağladı. Yazdırma belgelerini daha fazla etkinleştirmek için, etkin belge kapsama (OLE 2,0 ile birlikte sunulmayan mevcut bir OLE tasarımı kullanılarak), `IPrint` genellikle belge türünün kalıcı durumunu yükleyebilecek herhangi bir nesne aracılığıyla kullanılabilen temel standart bir yazdırma arabirimi sunar. Etkin bir belgenin her bir görünümü, `IPrint` Bu özellikleri sağlamak için isteğe bağlı olarak arabirimi destekleyebilir.

`IPrint`Arabirim aşağıdaki gibi tanımlanır:

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

İstemciler ve kapsayıcılar yalnızca belge yüklendikten `IPrint::Print` sonra belgenin kendisini yazdırmasını, yazdırma denetim bayraklarını, hedef cihazı, yazdırılacak sayfaları ve ek seçenekleri belirtmek için kullanılır. İstemci Ayrıca, arabirim üzerinden yazdırmanın devamını denetleyebilir `IContinueCallback` (aşağıya bakın).

Ayrıca, `IPrint::SetInitialPageNum` sayfaları sorunsuz bir şekilde numaralandırarak bir dizi belgeyi yazdırma özelliğini destekler, bu da Office Ciltçi gibi etkin belge kapsayıcıları avantajına açıktır. `IPrint::GetPageInfo` , çağıranın daha önce geçirilen başlangıç sayfası numarasını `SetInitialPageNum` (veya belgenin iç varsayılan başlangıç sayfası numarası) ve belgedeki sayfa sayısını almasına izin vererek sayfalandırma bilgilerinin basit görüntülenmesini sağlar.

Destekleyen nesneler, `IPrint` kayıt defterinde NESNENIN CLSID altında depolanan "yazdırılabilir" anahtarıyla işaretlenir:

HKEY_CLASSES_ROOT\CLSID\\ {...} \ Yazdırılabilir

`IPrint` genellikle ya da destekleyen aynı nesne üzerinde uygulanır `IPersistFile` `IPersistStorage` . Çağıranlar, "yazdırılabilir" anahtarı için kayıt defterine bakarak bazı bir sınıfın kalıcı durumunu program aracılığıyla nasıl yazdırabileceğinizi göz önünde. Şu anda, "yazdırılabilir" desteği en az ' `IPrint` ı gösterir; diğer arabirimler gelecekte tanımlanacağından `QueryInterface` `IPrint` temel destek düzeyini temsil eder.

Yazdırma yordamı sırasında, yazdırma işlemini başlatan istemcinin veya kapsayıcının, yazdırmanın devam edip etmediğini denetlemesini isteyebilirsiniz. Örneğin, kapsayıcı, yazdırma işini mümkün olan en kısa sürede sonlanacak bir "yazdırmayı Durdur" komutu destekleyebilir. Bu özelliği desteklemek için, yazdırılabilir bir nesnenin istemcisi arabirimiyle küçük bir bildirim havuzu nesnesi uygulayabilir `IContinueCallback` :

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

Bu arabirim, Win32 API çeşitli devamlılık yordamlarının yerini alan genel devamlılık geri çağırma işlevi olarak (örneğin, `AbortProc` yazdırma için ve `EnumMetafileProc` meta dosyası numaralandırması için) yararlı olacak şekilde tasarlanmıştır. Bu nedenle, bu arabirim tasarımı çok çeşitli zaman alan işlemlerde yararlı olur.

Çoğu genel durumda, `IContinueCallback::FContinue` işlevi uzun bir işlem tarafından düzenli aralıklarla çağrılır. Havuz nesnesi işleme devam etmek için S_OK döndürür ve yordamı en kısa sürede durdurmak için S_FALSE.

`FContinue`Ancak,, öğesinin bağlamında kullanılmaz `IPrint::Print` ; bunun yerine, yazdırma kullanır `IContinueCallback::FContinuePrint` . Herhangi bir yazdırma nesnesi düzenli aralıklarla `FContinuePrinting` , yazdırılan sayfa sayısını, Yazdırılmakta olan sayfanın sayısını ve istemcinin kullanıcıya görüntülemeyi seçebilecekleri yazdırma durumunu tanımlayan ek bir dizeyi ("sayfa 5/19" gibi) düzenli olarak çağırmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Etkin belge kapsayıcıları](../mfc/active-document-containers.md)
