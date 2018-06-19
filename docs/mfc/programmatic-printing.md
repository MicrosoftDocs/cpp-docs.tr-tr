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
ms.openlocfilehash: a439080cec7f3ae96014e9df6ddc65782686bf0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352841"
---
# <a name="programmatic-printing"></a>Program Aracılığıyla Yazdırma
OLE sağlanan kalıcı belgeleri benzersiz şekilde tanımlamak için anlamına gelir (**GetClassFile**) ve bunların ilişkili koda yükleyin (`CoCreateInstance`, **QueryInterface(IID_IPersistFile)**, **QueryInterface(IID_IPersistStorage)**, **IPersistFile::Load**, ve **IPersistStorage::Load**). Etkin belge kapsaması (OLE 2.0 ilk olarak gönderilmeyen varolan bir OLE tasarımı kullanarak) daha fazla yazdırma belgeleri etkinleştirmek için bir temel standart yazdırma arabirimi tanıtır `IPrint`, yükleyebilir herhangi bir nesne aracılığıyla genel olarak kullanılabilir kalıcı durum belge türü. Etkin belge her görünümünü isteğe bağlı olarak destekleyebilir **IPrint** bu yetenekleri sağlamak için arabirim.  
  
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
  
 İstemcileri ve kapsayıcılar yalnızca kullanır **IPrint::Print** belirtme yazdırma denetim bayrakları, hedef aygıt, yazdırmak için sayfa bu belge yüklendikten sonra kendisini yazdırmak için belge istemek ve ek seçenekler. İstemci yazdırma arabiriminden devamlılık kontrol edebilirsiniz `IContinueCallback` (aşağıya bakın).  
  
 Ayrıca, **IPrint::SetInitialPageNum** bir numaralandırma sorunsuz bir şekilde, açıkça Office Binder gibi etkin belge kapsayıcıları için bir avantajı sayfalar gibi bir dizi belgeleri yazdırma özelliğini destekler. **IPrint::GetPageInfo** başlangıç almak arayan vererek sayfalandırma bilgileri basit görüntüleme yapar sayfa numarası daha önce geçirilen **SetInitialPageNum** (veya varsayılan belge iç Sayfa numarası'den başlayarak) ve belgedeki sayfa sayısı.  
  
 Nesneleri destekleyen `IPrint` kayıt defterinde nesnenin CLSID altında depolanan "Printable" anahtarı ile işaretlenir:  
  
 HKEY_CLASSES_ROOT\CLSID\\{...} \Printable  
  
 `IPrint` genellikle ya da destekler aynı nesne üzerinde uygulanan `IPersistFile` veya `IPersistStorage`. Arayanlar "Printable" anahtarı için kayıt defterinde bakarak bazı sınıfı kalıcı durumunu program aracılığıyla yazdırma olanağı unutmayın. Şu anda "Yazdırılabilir" için destek en az gösterir `IPrint`; diğer arabirimleri gelecekte bu ardından ile de kullanılabilir olur tanımlanabilir `QueryInterface` nerede **IPrint** yalnızca temel düzeyde desteği temsil eder.  
  
 Yazdırma işlemi sırasında istemci veya yazdırma devam denetlemek için yazdırma başlatılan kapsayıcı isteyebilirsiniz. Örneğin, kapsayıcı yazdırma işi mümkün olan en kısa sürede sonlanmalıdır "yazdırma Durdur" bir komutu destekleyebilir. Bu özelliği desteklemek için istemcinin yazdırılabilir nesnesinin bir küçük Bildirim havuzu nesnesi arabirimi uygulayabilirsiniz `IContinueCallback`:  
  
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
  
 Bu arabirim Win32 API çeşitli devamlılık yordamlarda gerçekleşir bir genel devamlılık geri çağırma işlevini yararlı olacak şekilde tasarlanmıştır (gibi **AbortProc** yazdırma için ve  **EnumMetafileProc** meta dosyası numaralandırması için). Bu nedenle bu arabirimi tasarımı çok çeşitli uzun süren işlem faydalı olur.  
  
 En genel durumlarda **IContinueCallback::FContinue** işlevi herhangi uzun bir işlem tarafından düzenli olarak çağrılır. Havuz nesnesi döndüren `S_OK` işleme devam etmek ve **S_FALSE** yordamı hemen durdurmak için.  
  
 **FContinue**, ancak bağlamında kullanılmaz **IPrint::Print**; bunun yerine, kullanan yazdırma **IContinueCallback::FContinuePrint**. Herhangi bir yazdırma nesnesi düzenli aralıklarla çağırmalıdır **FContinuePrinting** yazdırma sayfa sayısı, yazdırılmasını sayfa sayısını ve istemci olabilir yazdırma durumu açıklayan ek bir dize geçirme Kullanıcı (örneğin, "19 sayfa 5") görüntülemek seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin Belge Kapsayıcıları](../mfc/active-document-containers.md)

