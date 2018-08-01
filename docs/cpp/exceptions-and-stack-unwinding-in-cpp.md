---
title: Özel durumları ve c++'ta yığın geriye doğru izleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cefb6ba2fe076714b420024ec09464fd928b63d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406392"
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++'da Özel Durumlar ve Yığını Geriye Doğru İzleme
C++ özel durum mekanizmasında denetim, throw deyiminden throw türünü işleyebilen ilk catch deyimine geçer. Catch deyimine ulaşıldığında, tüm kapsamda arasında throw ve catch deyimleri otomatik değişkenler olarak da bilinen bir işlemle yok edilir *yığın geriye doğru izleme*. Yığın geriye doğru izleme işleminde, yürütme aşağıdaki gibi olur:  
  
1.  Denetim ulaştığında **deneyin** normal sıralı yürütme deyimi. Korunan bölüm **deneyin** bloğu yürütülür.  
  
2.  Korunan bölümün yürütülmesi sırasında hiçbir özel durum oluşturulursa **catch** izleyin yan tümceleri **deneyin** blok yürütülmez. Yürütme devam eder en son deyimindeki **catch** ilişkili aşağıdaki yan tümcesi **deneyin** blok.  
  
3.  Korunan bölümün doğrudan veya dolaylı olarak çağırdığı bir yordam veya korunan bölümün yürütülmesi sırasında bir özel durum, bir özel durum nesnesi tarafından oluşturulan nesneden oluşturulur **throw** işlenen. (Bu, bir kopya oluşturucusunu da işin içine katabilir.) Bu noktada derleyici arar bir **catch** yan tümcesinde bir özel durum türü ya da işleyebilir daha yüksek bir yürütme bağlamı bir **catch** her türden özel durumu işleyebilen bir işleyici. **Catch** işleyicileri sonra görünme sırasına göre incelenir **deneyin** blok. Uygun bir işleyici bulunduğunda, sonraki dinamik olarak kapsayan **deneyin** bloğu incelenir. Bu işlem en dıştaki kapsayan kadar devam eder. **deneyin** bloğu incelenir.  
  
4.  Eşleşen bir işleyici hala bulunamazsa ya da geriye doğru işlem sırasında işleyici denetimi almadan önce bir özel durum oluşursa, önceden tanımlanmış çalışma zamanı işlevi `terminate` çağrılır. Özel durum, geriye doğru izleme başlamadan önce ve bir özel durum oluştuktan sonra oluşursa, `terminate` çağrılır.  
  
5.  Eşleşen bir **catch** işleyicisi bulunursa ve değere göre yakalarsa, özel durum nesnesi kopyalanarak biçimsel parametresi başlatılır. Başvuruya göre yakalarsa, parametre özel durum nesnesine başvurmak için başlatılır. Biçimsel parametre başlatıldıktan sonra, yığını geriye doğru izleme işlemi başlar. Bu tam olarak oluşturulmuş tüm otomatik nesnelerin yok edilmesi içerir; ancak henüz imha — başlangıcı arasındaki **deneyin** ilişkili olduğu blok **catch** işleyicisi ve özel durumun atar. Yok etme işlemi oluşturma işleminin ters sırasıyla yapılır. **Catch** işleyicisi yürütülür ve program son işleyiciden sonra yürütmeye devam eder; diğer bir deyişle, ilk deyim veya olmayan yapısı, bir **catch** işleyici. Denetim yalnızca girebilirsiniz bir **catch** işleyici oluşturulan bir özel durumla hiçbir zaman aracılığıyla bir **goto** deyimi veya bir **çalışması** etiketi bir **geçiş** deyimi.  
  
## <a name="stack-unwinding-example"></a>Yığın Geriye Doğru İzleme Örneği  
 Aşağıdaki örnek, bir özel durum oluştuğunda yığının nasıl geriye doğru izlediğini gösterir. İş parçacığı üzerindeki yürütme, `C` içindeki throw deyiminden `main` içindeki catch deyimine atlar ve yol boyunca her işlevi geriye doğru alır. `Dummy` nesnelerinin oluşturulduğu ve ardından kapsam dışına çıkarken yok edildikleri sıralamaya dikkat edin. Ayrıca, catch deyimini içeren `main` haricinde, hiçbir işlevin tamamlamadığına dikkat edin. `A` işlevi `B()` için yaptığı çağrıdan, `B` işlevi de `C()` için yaptığı çağrıdan hiçbir zaman dönmez. `Dummy` işaretçisine ve ilişkili delete deyiminin tanımına ilişkin açıklamayı kaldırır ve ardından programı çalıştırırsanız, işaretçinin asla silinmediğine dikkat edin. Bu, işlevler özel durum sağlamadığında neler olabileceğini gösterir. Daha fazla bilgi için bkz. Nasıl yapılır: Özel Durumlar için Tasarım. Catch deyimi için açıklama satırı yaparsanız, işlenmemiş bir özel durum nedeniyle bir program sonlandığında ne olacağını görebilirsiniz.  
  
```cpp 
#include <string>  
#include <iostream>  
using namespace std;  
  
class MyException{};  
class Dummy  
{  
    public:  
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }  
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }  
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }  
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }  
    string MyName;   
    int level;  
};  
  
void C(Dummy d, int i)  
{   
    cout << "Entering FunctionC" << endl;  
    d.MyName = " C";  
    throw MyException();     
  
    cout << "Exiting FunctionC" << endl;  
}  
  
void B(Dummy d, int i)  
{  
    cout << "Entering FunctionB" << endl;  
    d.MyName = "B";  
    C(d, i + 1);     
    cout << "Exiting FunctionB" << endl;   
}  
  
void A(Dummy d, int i)  
{   
    cout << "Entering FunctionA" << endl;  
    d.MyName = " A" ;  
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!  
    B(d, i + 1);  
 //   delete pd;   
    cout << "Exiting FunctionA" << endl;     
}  
  
int main()  
{  
    cout << "Entering main" << endl;  
    try  
    {  
        Dummy d(" M");  
        A(d,1);  
    }  
    catch (MyException& e)  
    {  
        cout << "Caught an exception of type: " << typeid(e).name() << endl;  
    }  
  
    cout << "Exiting main." << endl;  
    char c;  
    cin >> c;  
}  
  
/* Output:  
    Entering main  
    Created Dummy: M  
    Copy created Dummy: M  
    Entering FunctionA  
    Copy created Dummy: A  
    Entering FunctionB  
    Copy created Dummy: B  
    Entering FunctionC  
    Destroyed Dummy: C  
    Destroyed Dummy: B  
    Destroyed Dummy: A  
    Destroyed Dummy: M  
    Caught an exception of type: class MyException  
    Exiting main.  
  
*/  
```  