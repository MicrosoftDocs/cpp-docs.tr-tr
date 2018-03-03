---
title: selectany | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- selectany_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d8b4a1a78fb8231d407e60ded2c6dea3f7c891d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="selectany"></a>selectany
**Microsoft özel**  
  
 Derleyici bildirilen genel veri öğesi (değişken veya nesne) bir çekme herhangi comdat'ı (paketlenmiş işlevi) olduğunu söyler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec( selectany ) declarator  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlantı zaman, bir comdat'ı birden çok tanımlarını görülüyorsa bağlayıcı birini seçer ve rest atar. Varsa bağlayıcı seçeneği [/OPT:REF](../build/reference/opt-optimizations.md) (iyileştirmeler) seçilir, sonra da comdat'ı eleme bağlayıcı çıktısında tüm başvurulmayan veri öğeleri kaldırmak için ortaya çıkar.  
  
 Oluşturucular ve atama genel işlevi veya bildiriminde statik yöntemler tarafından başvuru oluşturmayın ve /OPT:REF eleme önlemez. Veriler için bir başvuruları varken yan etkileri gibi kodundan bağımlı değil.  
  
 Dinamik olarak başlatılan, genel nesneler için `selectany` başvurulmayan nesnenin başlatma kodu de atar.  
  
 Genel veri öğesi, bir EXE ya da DLL projesinde normalde bir yalnızca bir kez başlatılabilir. `selectany`aynı başlığını birden fazla kaynak dosyasında görüntülendiğinde üstbilgileri tarafından tanımlanan genel veri başlatma içinde kullanılabilir. `selectany`C ve C++ Derleyicileri içinde kullanılabilir.  
  
> [!NOTE]
>  `selectany`yalnızca dışarıdan görünür olan genel veri öğeleri gerçek başlatma için uygulanabilir.  
  
## <a name="example"></a>Örnek  
 Bu kodu nasıl kullanılacağını gösterir `selectany` özniteliği:  
  
```  
//Correct - x1 is initialized and externally visible   
__declspec(selectany) int x1=1;  
  
//Incorrect - const is by default static in C++, so   
//x2 is not visible externally (This is OK in C, since  
//const is not by default static in C)  
const __declspec(selectany) int x2 =2;  
  
//Correct - x3 is extern const, so externally visible  
extern const __declspec(selectany) int x3=3;  
  
//Correct - x4 is extern const, so it is externally visible  
extern const int x4;  
const __declspec(selectany) int x4=4;  
  
//Incorrect - __declspec(selectany) is applied to the uninitialized  
//declaration of x5  
extern __declspec(selectany) int x5;  
  
// OK: dynamic initialization of global object  
class X {  
public:  
X(int i){i++;};  
int i;  
};  
  
__declspec(selectany) X x(1);  
```  
  
## <a name="example"></a>Örnek  
 Bu kodu nasıl kullanılacağını gösterir `selectany` de kullandığınızda veri comdat'ı Katlama emin olmak için öznitelik [/OPT:ICF](../build/reference/opt-optimizations.md) bağlayıcı seçeneği. Veri ile işaretlenmelidir Not `selectany` ve içinde yerleştirilen bir **const** (salt okunur) bölümü. Salt okunur bölümünde açıkça belirtmeniz gerekir.  
  
```  
// selectany2.cpp  
// in the following lines, const marks the variables as read only  
__declspec(selectany) extern const int ix = 5;  
__declspec(selectany) extern const int jx = 5;  
int main() {  
   int ij;  
   ij = ix + jx;  
}  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)