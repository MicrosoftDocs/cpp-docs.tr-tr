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
ms.openlocfilehash: c7976d0ea22a0bf6f59b020f892d407c4721b9a7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652363"
---
# <a name="ftmbasegetmarshalsizemax-method"></a>FtmBase::GetMarshalSizeMax Metodu
Belirtilen nesneyi belirtilen arabirim işaretçisini hazırlamak için gereken bayt sayısı üst sınırı alın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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