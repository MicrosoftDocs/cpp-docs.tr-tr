---
title: CA2WEX sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 218e0d8f5e93a9e6c41ff855ff086cc7bfa6c766
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ca2wex-class"></a>CA2WEX sınıfı
Bu sınıf dize dönüştürme makroları tarafından kullanılan `CA2TEX`, `CA2CTEX`, `CT2WEX`, ve `CT2CWEX`ve typedef **CA2W**.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <int t_nBufferLength = 128>
class CA2WEX
```  
  
#### <a name="parameters"></a>Parametreler  
 `t_nBufferLength`  
 Çeviri işleminde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2WEX::CA2WEX](#ca2wex)|Oluşturucu.|  
|[CA2WEX:: ~ CA2WEX](#dtor)|Yok Edicisi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2WEX::operator LPWSTR](#operator_lpwstr)|Dönüşüm işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2WEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|  
|[CA2WEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabelleği.|  
  
## <a name="remarks"></a>Açıklamalar  
 Fazladan işlevsellik gerekli olmadığı sürece kullanmak `CA2TEX`, `CA2CTEX`, `CT2WEX`, `CT2CWEX`, veya **CA2W** kodunuzda.  
  
 Bu sınıf dönüştürme işleminin sonucu depolamak için kullanılan bir sabit boyutlu statik arabellek içerir. Bellek kullanarak sınıfı sonucu statik belleğe sığmayacak kadar büyük olursa ayırır `malloc`, nesne kapsam dışına çıktığında bellek boşaltma. Bu, metin dönüşüm makroları önceki sürümlerinde ATL, bu sınıfın Döngülerde kullanmak güvenli ve yığın taşması olmaz sağlar.  
  
 Sınıf başarısız olur ve yığın bellek çalışırsa, çağrı `AtlThrow` bağımsız değişkeni ile **E_OUTOFMEMORY**.  
  
 Varsayılan olarak, ATL dönüştürme sınıfları ve makroları geçerli iş parçacığının ANSI kod sayfası dönüştürme için kullanın. Belirli bir dönüştürme için bu davranışı geçersiz kılmak istiyorsanız, sınıf oluşturucusu ikinci parametre olarak kod sayfası belirtin.  
  
 Aşağıdaki makroları bu sınıfa bağlıdır:  
  
- `CA2TEX`  
  
- `CA2CTEX`  
  
- `CT2WEX`  
  
- `CT2CWEX`  
  
 Aşağıdaki typedef bu sınıfa bağlıdır:  
  
- **CA2W**  
  
 Bu metin dönüşüm makroları tartışma için bkz [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlconv.h  
  
##  <a name="ca2wex"></a>  CA2WEX::CA2WEX  
 Oluşturucu.  
  
```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Dönüştürülecek metin dizesi.  
  
 `nCodePage`  
 Kod sayfası dönüştürme gerçekleştirmek için kullanılır. Kod sayfası parametre hakkında bilgi için Windows SDK işlevi bkz [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) daha fazla ayrıntı için.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeviri işleminde kullanılan arabellek ayırır.  
  
##  <a name="dtor"></a>  CA2WEX:: ~ CA2WEX  
 Yok Edicisi.  
  
```
~CA2WEX() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış arabelleğe boşaltır.  
  
##  <a name="m_psz"></a>  CA2WEX::m_psz  
 Kaynak dizesi depolar veri üyesi.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CA2WEX::m_szBuffer  
 Dönüştürülmüş dizeyi depolamak için kullanılan statik arabelleği.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>  CA2WEX::operator LPWSTR  
 Dönüşüm işleci.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin dizesini türü olarak döndürür **LPWSTR.**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)   
 [CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
