---
title: CW2AEX sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13b6531dd1299235a125b1c25b0b1d84781755ed
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217846"
---
# <a name="cw2aex-class"></a>CW2AEX sınıfı
Bu sınıf, dize dönüşüm makroları CT2AEX, CW2TEX, CW2CTEX ve CT2CAEX ve typedef CW2A tarafından kullanılır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<int t_nBufferLength = 128>  
class CW2AEX
```  
  
#### <a name="parameters"></a>Parametreler  
 *t_nBufferLength*  
 Çeviri işlemde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2AEX::CW2AEX](#cw2aex)|Oluşturucu.|  
|[CW2AEX:: ~ CW2AEX](#dtor)|Yıkıcı.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2AEX::operator LPSTR](#operator_lpstr)|Dönüştürme işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2AEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|  
|[CW2AEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dize depolamak için kullanılan statik arabelleği.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ek işlevler gerekmiyorsa CT2AEX, CW2TEX, CW2CTEX, CT2CAEX veya CW2A kodunuzda kullanın.  
  
 Bu sınıf, dönüştürmenin sonucu depolamak için kullanılan sabit boyutlu bir statik arabellek içerir. Sonucu statik arabelleğe sığamayacak kadar büyük olursa, sınıfı kullanarak bellek ayırır **malloc**, nesne kapsam dışına çıktığında bellek boşaltma. Bu, metin dönüşüm makroları önceki sürümlerinde ATL, bu sınıf Döngülerde güvenlidir ve stack overflow olmaz sağlar.  
  
 Sınıfı başarısız olur ve yığın bellek çalışırsa, çağrı `AtlThrow` E_OUTOFMEMORY bağımsız.  
  
 Varsayılan olarak, geçerli iş parçacığının ANSI kod sayfasına dönüştürme için ATL dönüştürme sınıfları ve makroları kullanın. Belirli bir dönüştürme için bu davranışı geçersiz kılmak istiyorsanız, kod sayfası sınıfı için oluşturucu ikinci parametre olarak belirtin.  
  
 Aşağıdaki makroları bu sınıfa bağlıdır:  
  
- CT2AEX  
  
- CW2TEX  
  
- CW2CTEX  
  
- CT2CAEX  
  
 Aşağıdaki tür tanımı bu sınıfa bağlıdır:  
  
- CW2A  
  
 Bu metin dönüşüm makroları bir tartışma için bkz [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlconv.h  
  
##  <a name="cw2aex"></a>  CW2AEX::CW2AEX  
 Oluşturucu.  
  
```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *psz*  
 Dönüştürülecek metin dizesi.  
  
 *nCodePage*  
 Dönüştürme gerçekleştirmek için kullanılan kod sayfası. Windows SDK'sı işlevi için kod sayfası parametresi tartışmalara bakın [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar) daha fazla ayrıntı için.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeviri işlemde kullanılan arabellek ayırır.  
  
##  <a name="dtor"></a>  CW2AEX:: ~ CW2AEX  
 Yıkıcı.  
  
```
~CW2AEX() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış ara belleğini serbest bırakır.  
  
##  <a name="m_psz"></a>  CW2AEX::m_psz  
 Kaynak dizesi depolar veri üyesi.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CW2AEX::m_szBuffer  
 Dönüştürülmüş dize depolamak için kullanılan statik arabelleği.  
  
```
char m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>  CW2AEX::operator LPSTR  
 Dönüştürme işleci.  
  
```  
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin dizesi LPSTR türü olarak döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)   
 [CA2WEX sınıfı](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
