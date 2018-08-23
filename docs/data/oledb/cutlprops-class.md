---
title: CUtlProps sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CUtlProps
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
- CUtlProps
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
dev_langs:
- C++
helpviewer_keywords:
- CUtlProps class
- GetPropValue method
- IsValidValue method
- OnInterfaceRequested method
- OnPropertyChanged method
- SetPropValue method
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0179bbc68bb6ed60f6fadf26f98be492c2eeb4c1
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42466068"
---
# <a name="cutlprops-class"></a>CUtlProps Sınıfı
OLE DB özelliği arabirimleri çeşitli özelliklerini uygular (örneğin, `IDBProperties`, `IDBProperties`, ve `IRowsetInfo`).  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 İçeren sınıf `BEGIN_PROPSET_MAP`.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  

## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetPropValue](#getpropvalue)|Bir özelliği bir özellik kümesinden alır.|  
|[Isvalidvalue](#isvalidvalue)|Bir özellik ayarlamadan önce bir değer doğrulamak için kullanılır.|  
|[Onınterfacerequested](#oninterfacerequested)|Bir tüketici bir nesne oluşturma arabirimde bir yöntemi çağırdığında, isteğe bağlı bir arabirim için istekleri işler.|  
|[OnPropertyChanged](#onpropertychanged)|Zincirleme özellikleri işlemek üzere bir özelliğe ayarladıktan sonra çağrılır.|  
|[SetPropValue](#setpropvalue)|Bir özelliği bir özellik kümesi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çoğu bu sınıf, bir uygulama ayrıntısı olduğunu.  
  
 `CUtlProps` dahili olarak özelliklerini ayarlamak için iki üyeleri içerir: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) ve [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Bir özellik kümesi eşlemede kullanılan makrolar hakkında daha fazla bilgi için bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) ve [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).  
  
## <a name="getpropvalue"></a> CUtlProps::GetPropValue
Bir özelliği bir özellik kümesinden alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pguidPropSet*  
 [in] PropSet GUİD'i.  
  
 *Dwpropıd*  
 [in] Özellik dizini.  
  
 *pvValue*  
 [out] Yeni özellik değerini içeren bir değişken için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `Failure` hata ve başarılıysa S_OK.

## <a name="isvalidvalue"></a> CUtlProps::ısvalidvalue
Bir özellik ayarlamadan önce bir değer doğrulamak için kullanılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *iCurSet*  
 Özellik kümesi dizi dizine; yalnızca bir özellik kümesi ise sıfır.  
  
 *pDBProp*  
 Özellik kimliği ve yeni değer bir [DBPROP](/previous-versions/windows/desktop/ms717970\(v=vs.85\)) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT. Varsayılan dönüş S_OK değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yaklaşık bir özelliği ayarlamak için kullanılacak olan değer üzerinde çalıştırmak istediğiniz herhangi bir doğrulama rutinleri varsa, bu işlev geçersiz kılmalıdır. Örneğin, geçerli bir değer belirlemek için bir parola tabloya karşı DBPROP_AUTH_PASSWORD doğrulama. 

## <a name="oninterfacerequested"></a> CUtlProps::onınterfacerequested
Bir tüketici bir yöntem bir nesne oluşturma arabirimleri çağırdığında, isteğe bağlı bir arabirim için istekleri işler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *riid*  
 [in] İstenen arabirimi için IID. Açıklamasını daha fazla ayrıntı için bkz. *riid* parametresinin `ICommand::Execute` içinde *OLE DB Programcının Başvurusu* (içinde *MDAC SDK*).  
  
### <a name="remarks"></a>Açıklamalar  
 `OnInterfaceRequested` bir tüketici bir yöntem bir nesne oluşturma arabirimleri çağırdığında, isteğe bağlı bir arabirim için tüketici isteklerini işler (gibi `IDBCreateSession`, `IDBCreateCommand`, `IOpenRowset`, veya `ICommand`). İstenen arabirim için karşılık gelen OLE DB özelliğini ayarlar. Örneğin, tüketici isterse `IID_IRowsetLocate`, `OnInterfaceRequested` ayarlar `DBPROP_IRowsetLocate` arabirimi. Bunun yapılması, satır kümesi oluşturma sırasında doğru durumda tutar.  
  
 Bu yöntem, tüketici çağırdığında çağırılır `IOpenRowset::OpenRowset` veya `ICommand::Execute`.  
  
 Bir tüketici bir nesneyi açan ve isteğe bağlı bir arabirim istekleri, sağlayıcı VARIANT_TRUE bu arabirimi ile ilişkilendirilmiş özelliği ayarlamanız gerekir. Özelliğe bağlı işleme izin verecek şekilde `OnInterfaceRequested` sağlayıcının önce çağrılır `Execute` yöntemi çağrılır. Varsayılan olarak, `OnInterfaceRequested` aşağıdaki arabirimlerinden işler:  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   `IConnectionPointContainer`  
  
-   `IRowsetScroll`  
  
 Diğer arabirimleri işlemek istiyorsanız, bu işlem işlevleri için veri kaynağı, oturum, komut veya satır kümesi sınıfı işlevinde geçersiz kılar. Geçersiz kılma özellikleri ayarlama, herhangi bir zincirleme özelliği de ayarlar emin olmak için normal set/get özellikleri arabirimler gitmesi gereken (bkz [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).  

## <a name="onpropertychanged"></a> CUtlProps::OnPropertyChanged
Zincirleme özellikleri işlemek üzere bir özelliğe ayarladıktan sonra çağrılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *iCurSet*  
 Özellik kümesi dizi dizine; yalnızca bir özellik kümesi ise sıfır.  
  
 *pDBProp*  
 Özellik kimliği ve yeni değer bir [DBPROP](/previous-versions/windows/desktop/ms717970\(v=vs.85\)) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT. Varsayılan dönüş S_OK değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yer işaretleri veya değerleri üzerinde başka bir özelliğin değerini, bağımlı olan güncelleştirmeler gibi zincirleme özellikleri işlemek istiyorsanız, bu işlev geçersiz kılmalıdır.  
  
### <a name="example"></a>Örnek  
 Bu işlevde harcanan, kullanıcının özellik kimliği alır `DBPROP*` parametresi. Artık, zincir bir özelliğe karşı kimliği karşılaştırmak mümkündür. Özellik bulunduğunda `SetProperties` artık diğer özelliğiyle birlikte ayarlanacak özelliği ile adlandırılır. Bir alır, bu durumda `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, veya `DBPROP_ORDEREDBOOKMARKS` ayarlanmış bir özelliği `DBPROP_BOOKMARKS` özelliği.  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]  
  
## <a name="setpropvalue"></a> CUtlProps::SetPropValue
Bir özelliği bir özellik kümesi ayarlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pguidPropSet*  
 [in] PropSet GUİD'i.  
  
 *Dwpropıd*  
 [in] Özellik dizini.  
  
 *pvValue*  
 [in] Yeni özellik değerini içeren bir değişken için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `Failure` hata ve başarılıysa S_OK. 

## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)