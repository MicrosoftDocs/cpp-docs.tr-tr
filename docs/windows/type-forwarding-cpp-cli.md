---
title: "Tür iletme (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type forwarding, Visual C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6898c011a4e2e907cd745ccb206b0e0f0b37e78f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="type-forwarding-ccli"></a>Tür İletme (C++/CLI)
*Tür iletme* derleme A. kullanan istemcilerin yeniden derleyin gerekli değildir sağlayacak şekilde, bir tür bir derlemeye (a derlemesi) başka bir derlemeye (derleme B) taşımanızı sağlar  
  
## <a name="all-platforms"></a>Tüm Platformlar  
 Bu özellik tüm çalışma zamanları desteklenmiyor.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Bu özellik, Windows çalışma zamanı'nda desteklenmiyor.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 Aşağıdaki kod örneği, tür iletme kullanımı gösterilmiştir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
#using "new.dll"  
[assembly:TypeForwardedTo(type::typeid)];  
```  
  
### <a name="parameters"></a>Parametreler  
 `new`  
 Tür tanımı taşıdığınız derleme.  
  
 `type`  
 Tür tanımı başka bir derlemeye taşıyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bileşen (derleme) gelir ve sonra istemci uygulamalar tarafından kullanılan, iletme türü bileşeni (derleme) başka bir derlemeye taşımak için güncelleştirilen bileşenin (ve gerekli ek derlemeleri) sevk türü ve istemci kullanabilirsiniz uygulamalar, yeniden derlenmesi olmadan çalışmaya devam edecektir.  
  
 Tür iletme yalnızca var olan uygulamalar tarafından başvurulan bileşen için çalışır. Bir uygulamayı yeniden oluşturduğunuzda uygulamada kullanılan türleri için uygun derleme başvurularını olmalıdır.  
  
 Bir türü (A) bir derlemeye ait iletirken eklemelisiniz `TypeForwardedTo` özniteliği bir derleme başvurusu yanı sıra, bu tür için. Başvuru derleme aşağıdakilerden birini içermelidir:  
  
-   Türü A. tanımı  
  
-   A `TypeForwardedTo` bir derleme başvurusu yanı sıra bir özniteliği.  
  
 İletilebilir türleri örnekleri şunlardır:  
  
-   ref sınıfları  
  
-   değer sınıfları  
  
-   numaralandırmalar  
  
-   arabirimler  
  
 Aşağıdaki türlerden iletemez:  
  
-   Genel türler  
  
-   Yerel türler  
  
-   İç içe geçmiş türler (iç içe geçmiş tür iletmek istiyorsanız, kendilerini kapsayan türle iletmek)  
  
 Ortak dil çalışma zamanı hedefleme herhangi bir dilde yazılan bir derleme bir türü iletebilirsiniz.  
  
 Bunu, derleme A.dll oluşturmak için kullanılan bir kaynak kodu dosyasının bir tür tanımı içeriyorsa (`ref class MyClass`), ve bu tür taşımak istediğiniz tanımı derleme B.dll musunuz:  
  
1.  Taşıma `MyClass` B.dll oluşturmak için kullanılan bir kaynak kodu dosyasının tanımını yazın.  
  
2.  Derleme B.dll oluşturma  
  
3.  Silme `MyClass` A.dll oluşturmak ve şununla değiştirin için kullanılan kaynak kodu tanımından yazın:  
  
    ```  
    #using "B.dll"  
    [assembly:TypeForwardedTo(MyClass::typeid)];  
    ```  
  
4.  Derleme A.dll oluşturma.  
  
5.  İstemci uygulamaları derlemeden A.dll kullanın.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**