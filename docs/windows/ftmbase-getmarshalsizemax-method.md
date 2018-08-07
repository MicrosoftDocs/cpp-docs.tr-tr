---
title: FtmBase::GetMarshalSizeMax metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
dev_langs:
- C++
helpviewer_keywords:
- GetMarshalSizeMax method
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c39c313f06bb4dd1f4dbc095df159a38625e9db8
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570220"
---
# <a name="ftmbasegetmarshalsizemax-method"></a>FtmBase::GetMarshalSizeMax Metodu
Belirtilen nesneyi belirtilen arabirim işaretçisini hazırlamak için gereken bayt sayısı üst sınırı alın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
### <a name="parameters"></a>Parametreler  
 *riid*  
 Sıralanması arabirimi tanımlayıcısını başvuru.  
  
 *BD*  
 Arabirim işaretçisi; sıralanması NULL olabilir.  
  
 *dwDestContext*  
 Belirtilen arabirim iptal edilecek olduğu hedef bağlamı.  
  
 Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.  
  
 Şu anda unmarshaling geçerli işlemin (MSHCTX_INPROC) başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlem içinde ortaya çıkabilir.  
  
 *pvDestContext*  
 Gelecekte kullanılmak üzere ayrılmış; NULL olmalıdır.  
  
 *mshlflags*  
 İstemci işlemine aktarılacak veri sıralanması olup olmadığını belirten bayrak — genellikle bu durum — burada, alınabilir birden çok istemci tarafından genel bir tablo yazılamaz veya okunamaz. Bir veya daha fazla MSHLFLAGS numaralandırma değerlerini belirtin.  
  
 *pSize*  
 Bu işlem tamamlandığında hazırlama akışa yazılacak veri miktarına üst sınırı için işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde E_FAIL veya e_noınterface.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase Sınıfı](../windows/ftmbase-class.md)