---
title: CEnumerator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
- GetMoniker
- CEnumerator.GetMoniker
- CEnumerator::GetMoniker
- ATL.CEnumerator.GetMoniker
- ATL::CEnumerator::GetMoniker
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
- Find method
- GetMoniker method
- Open method
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 37d53932a283ea047d748985a1da348d9346ce1e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336972"
---
# <a name="cenumerator-class"></a>CEnumerator Sınıfı
Kullanıma sunan bir OLE DB sabit listesi nesnesi kullanan [ISourcesRowset](https://msdn.microsoft.com/library/ms715969.aspx) tüm veri kaynaklarını ve numaralandırıcıları açıklayan bir satır kümesi döndürmek için arabirim.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Bul](#find)|Belirtilen ada sahip bir arayan yok sağlayıcıları (veri kaynakları) arar.|  
|[GetMoniker](#getmoniker)|Alır `IMoniker` geçerli kayıt için arabirim.|  
|[açın](#open)|Numaralandırıcı açılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Alabileceğiniz `ISourcesRowset` dolaylı olarak bu sınıftaki veri.  

## <a name="find"></a> CEnumerator::Find
Belirtilen bir adı yok sağlayıcıları arasında arar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
bool Find(TCHAR* szSearchName) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *szSearchName*  
 [in] Aranacak ad.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** adı bulunursa. Aksi takdirde, **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ad eşlendiği `SOURCES_NAME` üyesi [ISourcesRowset](https://msdn.microsoft.com/library/ms715969.aspx) arabirimi.  
  
## <a name="getmoniker"></a> CEnumerator::GetMoniker
Görünen ad, bilinen adı dönüştürülebilir dize bileşeninin ayıklanacağı ayrıştırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT GetMoniker(LPMONIKER* ppMoniker) const throw();  

HRESULT GetMoniker(LPMONIKER* ppMoniker,   
   LPCTSTR lpszDisplayName) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *ppMoniker*  
 [out] Adı görünen adı ayrıştırıldı ([CEnumeratorAccessor::m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)) geçerli satır.  
  
 *lpszDisplayName*  
 [in] Ayrıştırılacak görünen adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  

## <a name="open"></a> CEnumerator::Open
Bir belirtilir ve ardından çağırarak satır kümesi için bir numaralandırıcı alır, numaralandırıcı için bilinen ad bağlar [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/library/ms711200.aspx).  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Open(LPMONIKER pMoniker) throw();  

HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();  

HRESULT Open(const CEnumerator& enumerator) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pMoniker*  
 [in] Bir işaretçi için bir numaralandırıcı için bir bilinen ad.  
  
 *pClsid*  
 [in] Bir işaretçi `CLSID` Numaralayıcı.  
  
 *Numaralandırıcı*  
 [in] Bir başvuru için bir numaralandırıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DBVIEWER](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)