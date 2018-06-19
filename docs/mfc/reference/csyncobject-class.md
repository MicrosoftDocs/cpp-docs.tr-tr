---
title: CSyncObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1712f0d26fc0d9ac3dcfb0f2a15a906351f43154
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374103"
---
# <a name="csyncobject-class"></a>CSyncObject sınıfı
Win32 eşitleme nesneleri için ortak işlevselliği sağlayan bir saf sanal sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](#csyncobject)|Oluşturan bir `CSyncObject` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSyncObject::Lock](#lock)|Eşitleme nesnesi erişim elde eder.|  
|[CSyncObject::Unlock](#unlock)|Eşitleme nesnesi erişim elde eder.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSyncObject::operator TANITICISI](#operator_handle)|Eşitleme nesnesi erişim sağlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSyncObject::m_hObject](#m_hobject)|Eşitleme nesnesini için tanıtıcı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Microsoft Foundation Class Kitaplığı türetilmiş çeşitli sınıflar sağlar `CSyncObject`. Bunlar [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), ve [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Makale eşitleme nesneleri kullanma hakkında daha fazla bilgi için bkz [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmt.h  
  
##  <a name="csyncobject"></a>  CSyncObject::CSyncObject  
 Verilen ada sahip bir eşitleme nesnesi oluşturur.  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrName`  
 Nesnenin adı. Varsa **NULL**, *pstrName* null olur.  
  
##  <a name="lock"></a>  CSyncObject::Lock  
 Eşitleme nesnesi tarafından denetlenen kaynak erişim kazanmak için bu işlevini çağırın.  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwTimeout`  
 Eşitleme nesnenin kullanılabilir olması için beklenecek süreyi milisaniye olarak süre miktarını belirtir (işaret). Varsa **SONSUZ**, `Lock` nesne döndürmeden önce işaret kadar bekler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşitleme nesnesi işaret edildiyse `Lock` başarıyla döndürür ve iş parçacığı şimdi nesnenin sahibi. Eşitleme nesnesi nonsignaled ise (kullanılamaz), `Lock` eşitleme nesne belirtilen milisaniye sayısı kadar işaret hale bekleyecek *dwTimeOut* parametresi. Eşitleme nesnesi belirtilen sürede, işaret hale değil, `Lock` hatasını döndürür.  
  
##  <a name="m_hobject"></a>  CSyncObject::m_hObject  
 Eşitleme nesnesini için tanıtıcı.  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="operator_handle"></a>  CSyncObject::operator TANITICISI  
 İşleyicisini almak için bu işleci kullanın `CSyncObject` nesnesi.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, eşitleme nesnesi; tanıtıcısı Aksi takdirde, **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows API'larını doğrudan çağırmak için tanıtıcı kullanabilirsiniz.  
  
##  <a name="unlock"></a>  CSyncObject::Unlock  
 Bildirimi `Unlock` saf sanal işlevi parametresiz olduğu ve türetme tüm sınıflar tarafından geçersiz kılınmalıdır `CSyncObject`.  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lCount`  
 Varsayılan uygulama tarafından kullanılmaz.  
  
 `lpPrevCount`  
 Varsayılan uygulama tarafından kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman varsayılan uygulaması döndürür **doğru**.  
  
### <a name="remarks"></a>Açıklamalar  
 İki parametre bildirimi her zaman varsayılan uygulamasını döndürür **doğru**. Bu işlev, çağıran iş parçacığı tarafından sahip olunan eşitleme nesneye erişimi serbest bırakmak için çağrılır. İkinci bildirim eşitleme nesneleri kontrollü bir kaynağa birden fazla erişime semafor gibi sağlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



