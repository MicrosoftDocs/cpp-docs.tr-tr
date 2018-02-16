---
title: CCommand::Open | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1a58dc67735a4f236c79ff6c777a4510dfdfcd12
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ccommandopen"></a>CCommand::Open
Yürütür ve isteğe bağlı olarak komut bağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `session`  
 [in] Oturumda hangi komutu yürütülemedi.  
  
 `wszCommand`  
 [in] Komutun yürütülmesi için bir UNICODE dizesi geçirildi. Olabilir **NULL** kullanırken `CAccessor`, geçirilen değerinden komutu; bu durumda alınır [DEFINE_COMMAND](../../data/oledb/define-command.md) makrosu. Bkz: [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) içinde *OLE DB Programcının Başvurusu* Ayrıntılar için.  
  
 `szCommand`  
 [in] Aynı `wszCommand` dışında bu parametre bir ANSI komut dizesini alır. Bu yöntemin dördüncü form NULL değerini alabilir. Ayrıntılar için bu konunun devamındaki "Açıklamalar" bakın.  
  
 *pPropSet*  
 [in] Bir dizi için bir işaretçi [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) özellikleri ve ayarlanacak değerleri içeren yapıları. Bkz: [özellik kümeleri ve özellik grupları](https://msdn.microsoft.com/en-us/library/ms713696.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK.  
  
 `pRowsAffected`  
 [Giriş/Çıkış] Burada bir komut tarafından etkilenen satırların sayımını döndürülen bellek için bir işaretçi. Varsa  *\*pRowsAffected* olan **NULL**, hiçbir satır sayısı döndürülür. Aksi takdirde, **açık** ayarlar *`pRowsAffected` aşağıdaki koşullara göre:  
  
|Eğer|Ardından|  
|--------|----------|  
|**CParamSets** öğesinin `pParams` 1'den büyük|*`pRowsAffected` Tüm yürütme belirtilen parametre kümeleri tarafından etkilenen satırların toplam sayısını temsil eder.|  
|Etkilenen satır sayısı kullanılamıyor|*`pRowsAffected` -1 olarak ayarlanır.|  
|Komut güncelleştirilmediği, silmek veya Satır Ekle|*`pRowsAffected` tanımlı değil.|  
  
 `guidCommand`  
 [in] Komut metni ayrıştırma için kullanılan sağlayıcının için genel kurallar ve sözdizimi belirtir bir GUID. Bkz: [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) ve [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) içinde *OLE DB Programcının Başvurusu* Ayrıntılar için.  
  
 `bBind`  
 [in] Yürütülen sonra komutu otomatik olarak bağlamak belirtir. Varsayılan değer **doğru**, otomatik olarak bağlanacak komutu neden olur. Ayarı `bBind` için **false** böylece el ile bağlayabilirsiniz komutu otomatik bağlama engeller. (El ile bağlama belirli OLAP kullanıcılara ilgilendirir.)  
  
 `ulPropSets`  
 [in] Sayısı [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) yapıları geçirilen *pPropSet* bağımsız değişkeni.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk üç formlarını **açık** bir oturum almak, bir komut oluşturun ve gerektiği gibi herhangi bir parametre bağlama komutu yürütün.  
  
 İlk biçimini **açık** Unicode komut dizesini alır ve varsayılan değeri yok.  
  
 İkinci biçiminde **açık** ANSI komut dizisi ve (varolan ANSI uygulamalarla geriye dönük uyumluluk için sağlanır) varsayılan bir değeri alır.  
  
 Üçüncü biçiminde **açık** nedeniyle türüne NULL olması komut dizesini sağlar `int` ile varsayılan değeri NULL. Arama için sağlanan `Open(session, NULL);` veya `Open(session);` NULL türünde olduğundan `int`. Bu sürüm gerektirir ve bu onaylar `int` parametresi NULL olmalıdır.  
  
 Dördüncü biçiminde kullanmak **açık** ne zaman bir komut oluşturmuş ve tek bir gerçekleştirmek istediğiniz [Prepare](../../data/oledb/ccommand-prepare.md) ve birden çok yürütmeleri.  
  
> [!NOTE]
>  **Açık** çağrıları **yürütme**, sırayla çağıran `GetNextResult`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCommand Sınıfı](../../data/oledb/ccommand-class.md)