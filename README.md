## GsonFormatNullValue

Modify gson format <https://github.com/zzz40500/GsonFormat>

if value is null return default value in getter method

String: return ""

List: return new ArrayList<>();

.etc

## Install

WiseGsonFormat.jar

## Example

### Json

```
{
    "name": "王五",
    "gender": "man",
    "age": 15,
    "height": "140cm",
    "addr": {
        "province": "fujian",
        "city": "quanzhou",
        "code": "300000"
    },
    "hobby": [
        {
            "name": "billiards",
            "code": "1"
        },
        {
            "name": "computerGame",
            "code": "2"
        }
    ]
}
```

### Bean

```
/**
     * name : 王五
     * gender : man
     * age : 15
     * height : 140cm
     * addr : {"province":"fujian","city":"quanzhou","code":"300000"}
     * hobby : [{"name":"billiards","code":"1"},{"name":"computerGame","code":"2"}]
     */

    private String name;
    private String gender;
    private int age;
    private String height;
    private AddrBean addr;
    private List<HobbyBean> hobby;

    public String getName() {
        if (TextUtils.isEmpty(name)) {
            name = "";
        }
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getGender() {
        if (TextUtils.isEmpty(gender)) {
            gender = "";
        }
        return gender;
    }

    public void setGender(String gender) {
        this.gender = gender;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getHeight() {
        if (TextUtils.isEmpty(height)) {
            height = "";
        }
        return height;
    }

    public void setHeight(String height) {
        this.height = height;
    }

    public AddrBean getAddr() {
        if (addr == null) {
            addr = new AddrBean();
        }
        return addr;
    }

    public void setAddr(AddrBean addr) {
        this.addr = addr;
    }

    public List<HobbyBean> getHobby() {
        if (hobby == null) {
            hobby = new ArrayList<>();
        }
        return hobby;
    }

    public void setHobby(List<HobbyBean> hobby) {
        this.hobby = hobby;
    }

    public static class AddrBean {
        /**
         * province : fujian
         * city : quanzhou
         * code : 300000
         */

        private String province;
        private String city;
        private String code;

        public String getProvince() {
            if (TextUtils.isEmpty(province)) {
                province = "";
            }
            return province;
        }

        public void setProvince(String province) {
            this.province = province;
        }

        public String getCity() {
            if (TextUtils.isEmpty(city)) {
                city = "";
            }
            return city;
        }

        public void setCity(String city) {
            this.city = city;
        }

        public String getCode() {
            if (TextUtils.isEmpty(code)) {
                code = "";
            }
            return code;
        }

        public void setCode(String code) {
            this.code = code;
        }
    }

    public static class HobbyBean {
        /**
         * name : billiards
         * code : 1
         */

        private String name;
        private String code;

        public String getName() {
            if (TextUtils.isEmpty(name)) {
                name = "";
            }
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }

        public String getCode() {
            if (TextUtils.isEmpty(code)) {
                code = "";
            }
            return code;
        }

        public void setCode(String code) {
            this.code = code;
        }
    }
```
