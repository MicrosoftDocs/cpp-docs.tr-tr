---
title: "CTypedPtrMap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
dev_langs: C++
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9056fc73e2718b2a21936c39e630f4d4fddf1eed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap sınıfı
Tür kullanımı uyumlu işaretçi eşleme sınıfların nesneler için "sarmalayıcı" sağlar `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, ve `CMapStringToPtr`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class BASE_CLASS, class KEY, class VALUE>  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Parametreler  
 `BASE_CLASS`  
 Yazılan işaretçi harita sınıfın temel sınıf; bir işaretçi eşleme sınıf olmalıdır ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, veya `CMapStringToPtr`).  
  
 `KEY`  
 Eşleme için anahtar olarak kullanılan nesne sınıfı.  
  
 `VALUE`  
 Eşlemesinde depolanan nesne sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Yineleme için sonraki öğeyi alır.|  
|[CTypedPtrMap::Lookup](#lookup)|Döndürür bir `KEY` dayalı bir `VALUE`.|  
|[CTypedPtrMap::RemoveKey](#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|  
|[CTypedPtrMap::SetAt](#setat)|Bir öğenin eşlemeye ekler; eşleşen bir anahtarı bulunursa, var olan öğenin yerini alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTypedPtrMap::operator]](#operator_at)|Bir öğenin eşlemeye ekler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullandığınızda `CTypedPtrMap`, C++ tür denetleme olanağı eşleşmeyen işaretçi türlerine göre neden olduğu hata ortadan kaldırmanıza yardımcı olur.  
  
 Çünkü tüm `CTypedPtrMap` işlevler satır içi, bu şablonu kullanımını boyutunu veya kodunuzu hızına önemli ölçüde etkilemez.  
  
 Kullanma hakkında daha fazla bilgi için `CTypedPtrMap`, makalelerine bakın [koleksiyonları](../../mfc/collections.md) ve [şablona dayalı sınıflar](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtempl.h  
  
##  <a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc  
 Harita öğesi alır `rNextPosition`, ardından güncelleştirmeleri `rNextPosition` harita sonraki öğe başvurmak için.  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `rPosition`  
 Bir başvuru belirtir bir **konumu** önceki tarafından döndürülen değer `GetNextAssoc` veya `BASE_CLASS` **:: GetStartPosition** çağırın.  
  
 *KEY*  
 Haritanın anahtarları türünü belirten bir şablon parametre.  
  
 `rKey`  
 Alınan öğenin döndürülen anahtarı belirtir.  
  
 *DEĞER*  
 Haritanın değerlerin türünü belirten bir şablon parametre.  
  
 `rValue`  
 Alınan öğenin döndürülen değerini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev eşlemesi tüm öğeler üzerinden yineleme için kullanışlıdır. Konum sırası mutlaka anahtar değeri dizisi ile aynı olduğunu unutmayın.  
  
 Alınan öğe Haritası son sonra yeni değeri ise `rNextPosition` ayarlanır **NULL**.  
  
 Bu satır içi işlev çağrılarını `BASE_CLASS` **:: GetNextAssoc**.  
  
##  <a name="lookup"></a>CTypedPtrMap::Lookup  
 `Lookup`map öğesi tam olarak eşleşen bir anahtara hızla bulmak için bir karma algoritması kullanır.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `BASE_CLASS`  
 Bu haritanın sınıfın temel sınıf belirten bir şablon parametre.  
  
 `key`  
 Bakılacak öğenin anahtarı.  
  
 *DEĞER*  
 Bu eşlemesinde depolanan değerlerin türü belirten bir şablon parametre.  
  
 `rValue`  
 Alınan öğenin döndürülen değerini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi bulunmazsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu satır içi işlev çağrılarını `BASE_CLASS` **:: arama**.  
  
##  <a name="operator_at"></a>CTypedPtrMap::operator]  
 Bu işleci yalnızca bir atama deyimi (bir l-değeri) sol tarafta kullanılabilir.  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>Parametreler  
 *DEĞER*  
 Bu eşlemesinde depolanan değerlerin türü belirten bir şablon parametre.  
  
 `BASE_CLASS`  
 Bu haritanın sınıfın temel sınıf belirten bir şablon parametre.  
  
 `key`  
 Aranan veya eşlemesinde oluşturulan öğenin anahtarı.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen anahtarı içeren herhangi bir harita öğe varsa, yeni bir öğe oluşturulur. Yoktur yok "sağ tarafında" (r) bu işleci için eşdeğer bir anahtar eşlemesinde bulunamayabilir olasılığı olduğundan. Kullanım `Lookup` öğesi alma için üye işlevi.  
  
##  <a name="removekey"></a>CTypedPtrMap::RemoveKey  
 Bu üye işlevi çağırır `BASE_CLASS` **:: RemoveKey**.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>Parametreler  
 *KEY*  
 Haritanın anahtarları türünü belirten bir şablon parametre.  
  
 `key`  
 Kaldırılacak öğenin anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş bulundu ve başarıyla kaldırıldı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).  
  
##  <a name="setat"></a>CTypedPtrMap::SetAt  
 Bu üye işlevi çağırır `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>Parametreler  
 *KEY*  
 Haritanın anahtarları türünü belirten bir şablon parametre.  
  
 `key`  
 NewValue anahtar değerini belirtir.  
  
 `newValue`  
 Yeni öğe değeri nesne işaretçisi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr sınıfı](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord sınıfı](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr sınıfı](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr Sınıfı](../../mfc/reference/cmapstringtoptr-class.md)
