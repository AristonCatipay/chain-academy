interface User {
  id: number
  name: string
}

interface AdminPermissions {
  admin: boolean
  role: string
}

type AdminUser = User & AdminPermissions

const admin: AdminUser = {
  id: 1,
  name: "Alex",
  admin: true,
  role: "Super Admin"
}

console.log("Admin:", admin)