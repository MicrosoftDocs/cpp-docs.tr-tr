---
title: CStrBufT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 695c3bc4c5e03f2ff6c1865f456b1ef358e3dcf4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cstrbuft-class"></a>CStrBufT sınıfı
Bu sınıf için otomatik kaynak temizleme sağlar `GetBuffer` ve `ReleaseBuffer` çağırır var olan `CStringT` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename TCharType>
class CStrBufT
```  
  
#### <a name="parameters"></a>Parametreler  
 *TCharType*  
 Karakter türü `CStrBufT` sınıfı. Aşağıdakilerden biri olabilir:  
  
- `char` (ANSI karakter dizelerini)  
  
- `wchar_t` (Unicode karakter dizelerini)  
  
- **TCHAR** (için ANSI ve Unicode karakter dizelerini)  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`PCXSTR`|Bir sabit dize için bir işaretçi.|  
|`PXSTR`|Bir dize için bir işaretçi.|  
|`StringType`|Bu sınıf şablonu özelleştirmeleri tarafından yönetilebilmesini, arabellek olan dize türü.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](#cstrbuft)|Dize arabellek nesnesi Oluşturucusu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStrBufT::SetLength](#setlength)|İlişkili dize nesnesi karakter arabellek uzunluğu ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|Alır bir **const** ilişkili dize nesnesi karakter arabelleğin işaretçi.|  
|[CStrBufT::operator PXSTR](#operator_pxstr)|Bir işaretçi ilişkili dize nesnesi karakteri arabelleğe alır.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStrBufT::AUTO_LENGTH](#auto_length)|Otomatik olarak yeni sürümde dize uzunluğunu belirler.|  
|[CStrBufT::SET_LENGTH](#set_length)|Dize nesnesi uzunluğunu GetBuffer zamanında ayarlama|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf çağrıları değiştirmek için bir sarmalayıcı sınıf olarak kullanılan [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), veya [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) ve `ReleaseBuffer`.  
  
 Öncelikle bir yardımcı sınıf olarak tasarlanmış `CStrBufT` hakkında endişelenmeden bir dize nesnesi karakter önbellekle çalışmak bir geliştirici için kullanışlı bir yol sağlayan veya çağrısı yapıldığında `ReleaseBuffer`. Sarmalayıcı nesne doğal olması durumunda bir özel durum ya da birden çok mevcut kod yol kapsam dışında olduğundan, bu mümkündür; dize kaynağı serbest bırakmak kendi yıkıcı neden oluyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpstr.h  
  
##  <a name="auto_length"></a>  CStrBufT::AUTO_LENGTH  
 Otomatik olarak yeni sürümde dize uzunluğunu belirler.  
  
```
static const DWORD AUTO_LENGTH = 0x01;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik olarak yeni sürümde dize uzunluğunu belirler. Dize null ile sonlandırılmış olmalıdır.  
  
##  <a name="cstrbuft"></a>  CStrBufT::CStrBufT  
 Arabellek nesnesi oluşturur.  
  
```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Arabellek ile ilişkili dize nesnesi. Genellikle, geliştirici, önceden tanımlanmış tür tanımları kullanır **CStrBuf** ( **TCHAR** değişken), **CStrBufA** ( `char` değişken) ve **CStrBufW**  ( `wchar_t` değişken).  
  
 *nMinLength*  
 En az karakter arabellek uzunluğu.  
  
 `dwFlags`  
 Dize uzunluğu otomatik olarak belirlenen belirler. Aşağıdakilerden biri olabilir:  
  
- **AUTO_LENGTH** dize uzunluğu, otomatik olarak ne zaman belirlenen [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) olarak adlandırılır. Dize null ile sonlandırılmış olmalıdır. Varsayılan değer.  
  
- **SET_LENGTH** dize uzunluğu ayarlanmış ne zaman [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) olarak adlandırılır.  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili dize nesnesi için string buffer oluşturur. Yapı sırasında [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) veya [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) olarak adlandırılır.  
  
 Kopya Oluşturucu olduğuna dikkat edin `private`.  
  
##  <a name="operator_pcxstr"></a>  CStrBufT::operator PCXSTR  
 C stili dize olarak ilişkili dize nesnesinde depolanan karakterlerin doğrudan erişir.  
  
```  
operator PCXSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesinin veri için bir karakter işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi bir dize nesnesi karakteri arabelleğe döndürmek için bu işlevini çağırın. Dize nesnesi içeriğini bu işaretçiyle değiştirilemez.  
  
##  <a name="operator_pxstr"></a>  CStrBufT::operator PXSTR  
 C stili dize olarak ilişkili dize nesnesinde depolanan karakterlerin doğrudan erişir.  
  
```
operator PXSTR() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesinin veri için bir karakter işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi bir dize nesnesi karakteri arabelleğe döndürmek için bu işlevini çağırın. Geliştirici Bu işaretçinin dize nesnesiyle içeriğini değiştirebilirsiniz.  
  
##  <a name="pcxstr"></a>  CStrBufT::PCXSTR  
 Bir sabit dize için bir işaretçi.  
  
```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```  
  
##  <a name="pxstr"></a>  CStrBufT::PXSTR  
 Bir dize için bir işaretçi.  
  
```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```  
  
##  <a name="set_length"></a>  CStrBufT::SET_LENGTH  
 Dize nesnede uzunluğunu ayarlama `GetBuffer` zaman.  
  
```
static const DWORD SET_LENGTH = 0x02;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dize nesnesi uzunluğu GetBuffer zaman ayarlayın.  
  
 Belirler [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) dize arabellek nesnesi oluşturulduğunda çağrılır.  
  
##  <a name="setlength"></a>  CStrBufT::SetLength  
 Karakter arabellek uzunluğu ayarlar.  
  
```
void SetLength(int nLength);
```  
  
### <a name="parameters"></a>Parametreler  
 `nLength`  
 Dize nesnesi karakter arabelleğin yeni uzunluğu.  
  
> [!NOTE]
>  Oluşturucuda belirtilen minimum arabellek uzunluğundan küçük veya buna eşit olmalıdır `CStrBufT`.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabellek nesnesiyle temsil edilen dize uzunluğu ayarlamak için bu işlevini çağırın.  
  
##  <a name="stringtype"></a>  CStrBufT::StringType  
 Bu sınıf şablonu özelleştirmeleri tarafından yönetilebilmesini, arabellek olan dize türü.  
  
```
typedef CSimpleStringT<TCharType> StringType;
```  
  
### <a name="remarks"></a>Açıklamalar  
 **TCharType** sınıf şablonu özelleştirmek için kullanılan karakter türü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)


