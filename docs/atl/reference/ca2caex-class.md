---
title: CA2CAEX sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3603f93c5b6430cd5aa11e4f43c99f75a838497
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879250"
---
# <a name="ca2caex-class"></a>CA2CAEX sınıfı
Bu sınıf, dize dönüşüm makroları CA2CTEX ve CT2CAEX ve typedef CA2CA tarafından kullanılır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>Parametreler  
 *t_nBufferLength*  
 Çeviri işlemde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2CAEX::CA2CAEX](#ca2caex)|Oluşturucu.|  
|[CA2CAEX:: ~ CA2CAEX](#dtor)|Yıkıcı.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|Dönüştürme işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2CAEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ek işlevler gerekmiyorsa, kendi kodunuzda CA2CTEX, CT2CAEX veya CA2CA kullanın.  
  
 Bu sınıf Döngülerde kullanmak güvenlidir ve stack overflow olmaz. Varsayılan olarak, ATL dönüştürme sınıfları ve makroları, geçerli iş parçacığının ANSI kod sayfasına dönüştürme için kullanır.  
  
 Aşağıdaki makroları bu sınıfa bağlıdır:  
  
- CA2CTEX  
  
- CT2CAEX  
  
 Aşağıdaki tür tanımı bu sınıfa bağlıdır:  
  
- CA2CA  
  
 Bu metin dönüşüm makroları bir tartışma için bkz [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlconv.h  
  
##  <a name="ca2caex"></a>  CA2CAEX::CA2CAEX  
 Oluşturucu.  
  
```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *psz*  
 Dönüştürülecek metin dizesi.  
  
 *nCodePage*  
 Bu sınıftaki kullanılmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeviri için gerekli arabellek oluşturur.  
  
##  <a name="dtor"></a>  CA2CAEX:: ~ CA2CAEX  
 Yıkıcı.  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış ara belleğini serbest bırakır.  
  
##  <a name="m_psz"></a>  CA2CAEX::m_psz  
 Kaynak dizesi depolar veri üyesi.  
  
```
LPCSTR m_psz;
```  
  
##  <a name="operator_lpcstr"></a>  CA2CAEX::operator LPCSTR  
 Dönüştürme işleci.  
  
```  
operator LPCSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin dizesi LPCSTR türü olarak döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)   
 [CA2WEX sınıfı](../../atl/reference/ca2wex-class.md)   
 [CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
