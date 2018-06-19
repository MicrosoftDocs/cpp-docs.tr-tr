---
title: CDataPathProperty sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
dev_langs:
- C++
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2559b4917f16bb8ddc49b73ace8bda6e1a9bafc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367314"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty sınıfı
Implements bir OLE zaman uyumsuz olarak yüklenen özelliğini denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Oluşturan bir `CDataPathProperty` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDataPathProperty::GetControl](#getcontrol)|İle ilişkili zaman uyumsuz OLE denetimi alır `CDataPathProperty` nesnesi.|  
|[CDataPathProperty::GetPath](#getpath)|Yol özellik adını alır.|  
|[CDataPathProperty::Open](#open)|Zaman uyumsuz özelliği ilişkili (OLE) ActiveX denetiminin yüklenmesini başlatır.|  
|[CDataPathProperty::ResetData](#resetdata)|Çağrıları `CAsyncMonikerFile::OnDataAvailable` denetim özelliklerini değiştirmiş kapsayıcı bildirir.|  
|[CDataPathProperty::SetControl](#setcontrol)|Özellik ile ilişkilendirilmiş zaman uyumsuz (OLE) ActiveX denetimi ayarlar.|  
|[CDataPathProperty::SetPath](#setpath)|Özelliğin yol adını ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman uyumsuz özellikler sonra zaman uyumlu başlatma yüklenir.  
  
 Sınıf `CDataPathProperty` türetildiği **CAysncMonikerFile**. Zaman uyumsuz Özellikler OLE denetimlerinde uygulamak için öğesinden bir sınıf türetin `CDataPathProperty`ve geçersiz kılma [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).  
  
 Zaman uyumsuz adlar ve ActiveX denetimlerini Internet uygulamalarında kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
  
- [Internet ilk adımlar: ActiveX denetimleri](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internet ilk adımlar: Zaman uyumsuz adlar](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
  
##  <a name="cdatapathproperty"></a>  CDataPathProperty::CDataPathProperty  
 Oluşturan bir `CDataPathProperty` nesnesi.  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pControl`  
 Bu ile ilişkilendirilmesi OLE denetim nesnesi için bir işaretçi `CDataPathProperty` nesnesi.  
  
 `lpszPath`  
 Mutlak veya göreli olabilir, yolun özelliği gerçek mutlak konumu başvuran zaman uyumsuz bir ad oluşturmak için kullanılır. `CDataPathProperty` URL'ler, değil dosya adlarını kullanır. İsterseniz bir `CDataPathProperty` nesne için bir dosya, başına `file://` yolu.  
  
### <a name="remarks"></a>Açıklamalar  
 `COleControl` Tarafından için nesne işaret `pControl` tarafından kullanılan **açık** ve türetilmiş sınıfları tarafından alınır. Varsa `pControl` olan **NULL**, ile kullanılan denetimi **açık** ile ayarlamalıdır `SetControl`. Varsa `lpszPath` olan **NULL**, yolundaki geçirebilirsiniz **açık** veya ile ayarlayın `SetPath`.  
  
##  <a name="getcontrol"></a>  CDataPathProperty::GetControl  
 Almak için bu üye işlevini çağırın `COleControl` ilişkili nesne `CDataPathProperty` nesne.  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE denetim için bir işaretçi ilişkili döndürür `CDataPathProperty` nesnesi. **NULL** denetimin değil ilişkiliyse.  
  
##  <a name="getpath"></a>  CDataPathProperty::GetPath  
 Yolun almak, ne zaman ayarlamak için bu üye işlevini çağırın `CDataPathProperty` nesne oluşturulan veya belirtilen **açık**, ya da önceki çağrıda belirtilen `SetPath` üye işlevi.  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yol adı özelliği için döndürür. Yol belirtilmişse boş olabilir.  
  
##  <a name="open"></a>  CDataPathProperty::Open  
 Zaman uyumsuz özelliği ilişkili denetiminin yüklenmesini başlatmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL Open(
    COleControl* pControl,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    COleControl* pControl,
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    CFileException* pError = NULL);  
  
virtual BOOL Open(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pControl`  
 Bu ile ilişkilendirilmesi OLE denetim nesnesi için bir işaretçi `CDataPathProperty` nesnesi.  
  
 `pError`  
 Dosya özel durumu için bir işaretçi. Bir hata olması durumunda, neden olacak şekilde ayarlanacaktır.  
  
 `lpszPath`  
 Mutlak veya göreli olabilir, yolun özelliği gerçek mutlak konumu başvuran zaman uyumsuz bir ad oluşturmak için kullanılır. `CDataPathProperty` URL'ler, değil dosya adlarını kullanır. İsterseniz bir `CDataPathProperty` nesne için bir dosya, başına `file://` yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev almaya çalıştığında `IBindHost` denetiminden arabirimi.  
  
 Çağırmadan önce **açık** olmadan yol, özelliğin yolu değer ayarlamanız gerekir. Nesne yapılandırılmış, veya çağırarak olduğunda bu yapılabilir `SetPath` üye işlevi.  
  
 Çağırmadan önce **açık** denetimi olmadan (daha önce bir OLE denetimi olarak bilinen) bir ActiveX denetimini nesne ile ilişkili olabilir. Nesne yapılandırılmış, veya çağırarak olduğunda bu yapılabilir `SetControl`.  
  
 Tüm aşırı [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) de mevcuttur `CDataPathProperty`.  
  
##  <a name="resetdata"></a>  CDataPathProperty::ResetData  
 Almak için bu işlevi çağırmak `CAsyncMonikerFile::OnDataAvailable` denetim özellikleri değiştirilmiştir ve zaman uyumsuz olarak yüklenen tüm bilgileri artık faydalıdır kapsayıcı bildirmek için.  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Açılış yeniden başlatılması. Türetilen sınıflar bu işlev farklı Varsayılanlar için geçersiz kılabilirsiniz.  
  
##  <a name="setcontrol"></a>  CDataPathProperty::SetControl  
 Zaman uyumsuz OLE denetimi ile ilişkilendirmek için bu üye işlevini çağırın `CDataPathProperty` nesnesi.  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>Parametreler  
 `pControl`  
 Özelliği ile ilişkilendirilmesi için zaman uyumsuz OLE denetimi için bir işaretçi.  
  
##  <a name="setpath"></a>  CDataPathProperty::SetPath  
 Özelliğin pathname ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPath`  
 Mutlak veya göreli zaman uyumsuz olarak yüklenen özelliğine olabilen bir yolu. `CDataPathProperty` URL'ler, değil dosya adlarını kullanır. İsterseniz bir `CDataPathProperty` nesne için bir dosya, başına `file://` yolu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örneği görüntüsü](../../visual-cpp-samples.md)   
 [CAsyncMonikerFile sınıfı](../../mfc/reference/casyncmonikerfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
