---
title: CW2CWEX sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 671311b0788438d7b92dad9d9137e28cbb88df60
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363288"
---
# <a name="cw2cwex-class"></a>CW2CWEX sınıfı
Bu sınıf dize dönüştürme makroları tarafından kullanılan `CW2CTEX` ve `CT2CWEX`ve typedef `CW2W`.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<int t_nBufferLength = 128>  
class CW2CWEX
```  
  
#### <a name="parameters"></a>Parametreler  
 `t_nBufferLength`  
 Çeviri işleminde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](#cw2cwex)|Oluşturucu.|  
|[CW2CWEX:: ~ CW2CWEX](#dtor)|Yok Edicisi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2CWEX::operator LPCWSTR](#operator_lpcwstr)|Dönüşüm işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2CWEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Fazladan işlevsellik gerekli olmadığı sürece kullanmak `CW2CTEX`, `CT2CWEX`, veya `CW2W` kodunuzda.  
  
 Bu sınıf Döngülerde güvenlidir ve yığın taşması olmaz. Varsayılan olarak, ATL dönüştürme sınıfları ve makroları geçerli iş parçacığının ANSI kod sayfası dönüştürme için kullanın.  
  
 Aşağıdaki makroları bu sınıfa bağlıdır:  
  
- `CW2CTEX`  
  
- `CT2CWEX`  
  
 Aşağıdaki typedef bu sınıfa bağlıdır:  
  
- `CW2W`  
  
 Bu metin dönüşüm makroları tartışma için bkz [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlconv.h  
  
##  <a name="cw2cwex"></a>  CW2CWEX::CW2CWEX  
 Oluşturucu.  
  
```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2CWEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Dönüştürülecek metin dizesi.  
  
 `nCodePage`  
 Kod sayfası. Bu sınıf kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeviri işleminde kullanılan arabellek ayırır.  
  
##  <a name="dtor"></a>  CW2CWEX:: ~ CW2CWEX  
 Yok Edicisi.  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış arabelleğe boşaltır.  
  
##  <a name="m_psz"></a>  CW2CWEX::m_psz  
 Kaynak dizesi depolar veri üyesi.  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="operator_lpcwstr"></a>  CW2CWEX::operator LPCWSTR  
 Dönüşüm işleci.  
  
```  
operator LPCWSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin dizesini türü olarak döndürür **LPCWSTR.**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)   
 [CA2WEX sınıfı](../../atl/reference/ca2wex-class.md)   
 [CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)   
 [CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
