---
title: CFixedStringT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93125d15be32a95d71c763f476fad700dab65a3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356993"
---
# <a name="cfixedstringt-class"></a>CFixedStringT sınıfı
Bu sınıf, bir dize nesnesi sabit karakter arabelleği ile temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>Parametreler  
 `StringType`  
 Sabit dize nesnesi için temel sınıf olarak kullanılan ve herhangi `CStringT`-temel türü. Bazı örnekler `CString`, `CStringA`, ve `CStringW`.  
  
 *t_nChars*  
 Arabellekte depolanan karakterlerin sayısı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Dize nesnesi Oluşturucusu.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|Yeni bir değer atayan bir `CFixedStringT` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf dayalı özel bir dize sınıf örnektir `CStringT`. Oldukça benzer rağmen iki sınıf uygulamasında farklılık gösterir. Arasındaki temel farklılıklar `CFixedStringT` ve `CStringT` şunlardır:  
  
-   İlk karakter arabellek nesnesinin bir parçası ayrılan ve boyutu *t_nChars*. Böylece **CFixedString** nesne bitişik bellek öbek performans amacıyla kaplar. Ancak, varsa içeriğini bir `CFixedStringT` nesne büyür ötesinde *t_nChars*, arabellek dinamik olarak ayrılır.  
  
-   İçin karakter arabellek bir `CFixedStringT` nesnesidir her zaman aynı uzunlukta ( *t_nChars*). Arabellek boyutu için herhangi bir kısıtlama `CStringT` nesneleri.  
  
-   Bellek Yöneticisi için `CFixedStringT` sağlayacak şekilde paylaşılmasını özelleştirilmiş bir [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) nesnesi iki veya daha fazla arasında `CFixedStringT` objectsis izin verilmiyor. `CStringT` nesneleri bu sınırlama yoktur.  
  
 Özelleştirme hakkında daha fazla bilgi için `CFixedStringT` ve dize nesneler için bellek yönetimi genel olarak, bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cstringt.h  
  
##  <a name="cfixedstringt"></a>  CFixedStringT::CFixedStringT  
 Oluşturan bir `CFixedStringT` nesnesi.  
  
```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Bu kopyalanacak null ile sonlandırılmış bir dize `CFixedStringT` nesnesi.  
  
 `str`  
 Var olan `CFixedStringT` bu kopyalanacak nesne `CFixedStringT` nesne.  
  
 `pStringMgr`  
 Bellek Yöneticisi'nin bir işaretçi `CFixedStringT` nesnesi. Daha fazla bilgi için `IAtlStringMgr` ve bellek yönetimi için `CFixedStringT`, bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucular yeni ayrılmış depolama alanına giriş verilerini kopyaladığından farkında olmalıdır, bellek özel durumlara neden olabilir. Bu oluşturucu bazıları dönüştürme işlevleri hareket unutmayın.  
  
##  <a name="operator__eq"></a>  CFixedStringT::operator =  
 Var olan yeniden başlatır `CFixedStringT` yeni veri nesnesi.  
  
```
CFixedStringT<StringType, t_nChars>& operator=(
  const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Bu kopyalanacak null ile sonlandırılmış bir dize `CFixedStringT` nesnesi.  
  
 `psz`  
 Var olan `CFixedStringT` bu kopyalanacak `CFixedStringT` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bilmeniz gereken her yeni depolama genellikle sonuç tutmak için ayrılmış olduğundan atama işleci kullandığınızda özel durumlar oluşabilir belleğin `CFixedStringT` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)




